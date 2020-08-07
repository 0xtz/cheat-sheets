# PyQt5 

## Load UI file 

```python
#!/usr/bin/python3

from PyQt5 import QtCore, QtGui, QtWidgets, uic
import sys

class MyApp(QtWidgets.QMainWindow):
    def __init__(self):
        super(MyApp, self).__init__()
        uic.loadUi('main.ui', self)
        self.ui()

    def ui(self):
    pass


def main():
    app = QtWidgets.QApplication(sys.argv)
    window = MyApp()
    window.show()
    sys.exit(app.exec_())


if __name__ == '__main__':
    main()

```
---

## Convert UI to PY 

```bash

pyuic5 main.ui -o Main.py

```
---
### ICONS
```
<RCC>
  <qresource prefix="16x16">
    <file>icons/cil-arrow-bottom.png</file>
  </qresource>
</RCC>
```
---
## Set ???

### WINDOW title :

```python
self.setWindowTitle('Main Window - Python Base')
```


