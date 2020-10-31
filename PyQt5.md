# PyQt5 

## Start Main && Load UI file 

```python
#!/usr/bin/python3

from PyQt5.QtGui import *
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.uic import loadUiType
import sys
# from main_ui import Ui_MainWindow

MainUI,_ = loadUiType('main.ui')

class Main(QMainWindow , MainUI):
    def __init__(self , parent=None):
        super(Main, self).__init__(parent)
        QMainWindow.__init__(self)
        self.setupUi(self)

def main():
    app = QApplication(sys.argv)
    window = Main()
    window.show()
    app.exec_()

if __name__ == '__main__':
    main()
```
---

## Convert UI to PY 

```bash

pyuic5 main.ui -o Main.py

```

## ICONS

```xml
<!DOCTYPE RCC><RCC version="1.0">
<qresource>
        <file>icons/xxx.png</file>
</qresource>
</RCC>
```
---
## Remove TITLE BAR :
```python

self.setWindowFlags(Qt.Window | Qt.CustomizeWindowHint

```

## WINDOW title :

```python

self.setWindowTitle('Main Window - Python Base')

```
## setting geometry 

```python
self.setGeometry(100, 100, 600, 400) 
```
### ProgressBar
```python3

self.ui.progressBar.setMinimum(0)
self.ui.progressBar.setMaximum(99)
self.ui.progressBar.setValue(0)

```
#### cercular
```css
QFrame{
	border-radius: 95px;	
	background-color: rgb(58, 58, 102);
}
```

### MOVE WINDOW
```python

class UIFunctions(MainWindow):

    ## ==> MAXIMIZE RESTORE FUNCTION
    def maximize_restore(self):
        global GLOBAL_STATE
        status = GLOBAL_STATE

        # IF NOT MAXIMIZED
        if status == 0:
            self.showMaximized()

            # SET GLOBAL TO 1
            GLOBAL_STATE = 1

            # IF MAXIMIZED REMOVE MARGINS AND BORDER RADIUS
            self.ui.btn_maximize.setToolTip("Restore")
        else:
            GLOBAL_STATE = 0
            self.showNormal()
            self.resize(self.width()+1, self.height()+1)
            self.ui.btn_maximize.setToolTip("Maximize")

    ## ==> UI DEFINITIONS
    def uiDefinitions(self):
   
        # MAXIMIZE / RESTORE
        self.ui.btn_maximize.clicked.connect(lambda: UIFunctions.maximize_restore(self))

        # MINIMIZE
        self.ui.btn_minimize.clicked.connect(lambda: self.showMinimized())

        # CLOSE
        self.ui.btn_close.clicked.connect(lambda: self.close())

    ## RETURN STATUS IF WINDOWS IS MAXIMIZE OR RESTAURED
    def returnStatus():
        return GLOBAL_STATE
        
# In the Class 
        # MOVE WINDOW
        def moveWindow(event):
            # RESTORE BEFORE MOVE
            if UIFunctions.returnStatus() == 1:
                UIFunctions.maximize_restore(self)

            # IF LEFT CLICK MOVE WINDOW
            if event.buttons() == Qt.LeftButton:
                self.move(self.pos() + event.globalPos() - self.dragPos)
                self.dragPos = event.globalPos()
                event.accept()

        # SET TITLE BAR
        self.ui.title_bar.mouseMoveEvent = moveWindow

        ## ==> SET UI DEFINITIONS
        UIFunctions.uiDefinitions(self)

```



--- 
# animation 

```python
class UIFunctions(MainWindow):

    def toggleMenu(self, maxWidth, enable):
        if enable:

            # GET WIDTH
            width = self.ui.frame_left_menu.width()
            maxExtend = maxWidth
            standard = 70

            # SET MAX WIDTH
            if width == 70:
                widthExtended = maxExtend
            else:
                widthExtended = standard

            # ANIMATION
            self.animation = QPropertyAnimation(self.ui.frame_left_menu, b"minimumWidth")
            self.animation.setDuration(400)
            self.animation.setStartValue(width)
            self.animation.setEndValue(widthExtended)
            self.animation.setEasingCurve(QtCore.QEasingCurve.InOutQuart)
            self.animation.start()

class MainWindow(QMainWindow):
    def __init__(self):
        ...

        ## TOGGLE/BURGUER MENU
        self.ui.Btn_Toggle.clicked.connect(lambda: UIFunctions.toggleMenu(self, 250, True))

        ## PAGES

        # PAGE 1
        self.ui.btn_page_1.clicked.connect(lambda: self.ui.stackedWidget.setCurrentWidget(self.ui.page_1))

        # PAGE 2
        self.ui.btn_page_2.clicked.connect(lambda: self.ui.stackedWidget.setCurrentWidget(self.ui.page_2))

        # PAGE 3
        self.ui.btn_page_3.clicked.connect(lambda: self.ui.stackedWidget.setCurrentWidget(self.ui.page_3))
            
            
```


--- 
# Styling 

```css
QPushButton {

}
QPushButton:hover {

}
QPushButton:pressed {

}
/* ------------------------------------ */

```
## Main Colors 
```css
background-color: rgb(77, 77, 127);

color: rgb(115, 185, 255); // Blue
color: rgb(115, 255, 171); // Green
color: rgb(255, 44, 174); // red

--------------------------
## TYTLE BAR   |-|o|x|

QPushButton {
	border: none;
	border-radius: 8px;	
	background-color: rgb(85, 255, 127);
}
QPushButton:hover {	
	background-color: rgba(85, 255, 127, 150);
}
----------------
QPushButton {
	border: none;
	border-radius: 8px;		
	background-color: rgb(255, 170, 0);
}
QPushButton:hover {	
	background-color: rgba(255, 170, 0, 150);
}
-----------------
QPushButton {
	border: none;
	border-radius: 8px;		
	background-color: rgb(255, 0, 0);
}
QPushButton:hover {		
	background-color: rgba(255, 0, 0, 150);
}

```


---
# BD

## Sqlite
```python
from PyQt5.QtSql import QSqlDatabase, QSqlQuery

# Executing SQL Statements
def createDB():
    db = QSqlDatabase.addDatabase("QSQLITE")
    db.setDatabaseName("/home/$USER/test.db")
    if db.open():
        query = QSqlQuery()
        query.exec_("create table person(id int primary key, name varchar(20), address varchar(30))")
        query.exec_("insert into person values(1, 'Bauer', 'beijing')")

        db.close()

```
