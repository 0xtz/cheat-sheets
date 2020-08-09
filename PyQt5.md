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
``python
self.ui.progressBar.setMinimum(0)
self.ui.progressBar.setMaximum(99)
self.ui.progressBar.setValue(0)
```

