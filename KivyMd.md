# kivy Md

What is KivyMD ??
https://github.com/HeaTTheatR/KivyMD
- Less code. More beautiful design

Material design ???
https://material.io/design/introduction

## start App

```python
from kivymd.app import MDApp
#class name == app_name :)
class DemoApp(MDApp):
    def build(self):
        return

DemoApp().run()
```
## Labels 

1) theme_colors
https://raw.githubusercontent.com/HeaTTheatR/KivyMD-data/master/gallery/kivymddoc/md-label-theme-text-color.png

2) Custom color
3) Styles
https://raw.githubusercontent.com/HeaTTheatR/KivyMD-data/master/gallery/kivymddoc/md-label-font-style.gif
4) MDIcons
https://github.com/HeaTTheatR/KivyMD/blob/master/kivymd/icon_definitions.py

```python
label = MDLabel(text="Hello world", halign="center", theme_text_color="Error",
                        font_style="Subtitle2")
label = MDLabel(text="Hello world", halign="center",theme_text_color="Custom",
                text_color=(0,0,1,1))
# icon
label = MDIcon(icon="language-python", halign="center")
```
# Buttons


