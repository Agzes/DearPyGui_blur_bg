# DearPyGui_blur_bg

! Move dpg_blur in folder of your project !

Example (decorate=True):
```python
" import dpg_blur"
from dpg_blur import WindowsWindowEffect, get_hwnd
import dearpygui.dearpygui as dpg

dpg.create_context()

" initializing the library "
window_effect = WindowsWindowEffect()

" creating a function that will be executed after the UI is rendered "
def after_init_ui():
    " making the background transparent "
    window_effect.setAeroEffect(get_hwnd())

" adding a function call after rendering the UI "
dpg.set_frame_callback(20, after_init_ui)

" creating a viewport with a transparent background 'clear_color=[0, 0, 0, 0]' "
dpg.create_viewport(title="Example", clear_color=[0, 0, 0, 0], height=100,width=100)
dpg.setup_dearpygui()
dpg.show_viewport()
while dpg.is_dearpygui_running():
    dpg.render_dearpygui_frame()
dpg.destroy_context()
```
Result:

![image](https://github.com/Agzes/DearPyGui_blur_bg/assets/103037173/aa0ebdb4-1eda-4fd3-9e1a-bd2b07948118)

Example (decorate=False):
```python
" import dpg_blur"
from dpg_blur import WindowsWindowEffect, get_hwnd
import dearpygui.dearpygui as dpg


dpg.create_context()

" initializing the library "
window_effect = WindowsWindowEffect()

" creating a function that will be executed after the UI is rendered "
def after_init_ui():
    " making the background transparent "
    window_effect.setAeroEffect(get_hwnd())
    " make Rounded Corners (for win11) "
    window_effect.setRoundedCorners(get_hwnd(), 10)

" adding a function call after rendering the UI "
dpg.set_frame_callback(20, after_init_ui)

" creating a viewport with a transparent background 'clear_color=[0, 0, 0, 0]' "
dpg.create_viewport(title="Example", decorated=False, clear_color=[0, 0, 0, 0], height=100,width=100)
dpg.setup_dearpygui()
dpg.show_viewport()
while dpg.is_dearpygui_running():
    dpg.render_dearpygui_frame()
dpg.destroy_context()
```
Result:

![image](https://github.com/Agzes/DearPyGui_blur_bg/assets/103037173/0be92131-8c58-4dcd-8760-4df5eb3f168d)
