<h1 align="center">DearPyGui_blur_bg
</a>
<h5 align="center">Micro-plugin to make background blur in DearPyGui on Windows</a>  
<br><br><br><br><br><br><br><br><br>
<h2 align="center">ɪɴsᴛᴀʟʟɪɴɢ</a></h2>
<h4 align="center">1 | download  <a href="https://github.com/Agzes/DearPyGui_blur_bg/releases/download/v.1.1/dpg_blur.py">dpg_blur.py</a> from  <a href="https://github.com/Agzes/DearPyGui_blur_bg/releases">releases</a> <br> 2 | put it in the same folder as your main.py <br> 3 | import it in your main.py <br>

<br><br>

<h2 align="center">ᴇxᴀᴍᴘʟᴇs</a></h2>


<h3 align="center">↙️ example with decorate ↘️</a></h3>

```python
from dpg_blur import WindowsWindowEffect, get_hwnd
import dearpygui.dearpygui as dpg

# Initialize DearPyGui context
dpg.create_context()

# Initialize the dpg_blur library
window_effect = WindowsWindowEffect()

# Function to apply the aero effect after UI is rendered
def after_init_ui():
    # Make the window background transparent
    window_effect.setAeroEffect(get_hwnd())

# Set function to be called after rendering the UI
dpg.set_frame_callback(5, after_init_ui)

# Create a viewport with transparent background (clear_color=[0, 0, 0, 0])
dpg.create_viewport(title="Example", clear_color=[0, 0, 0, 0], height=100, width=100)

# Setup and display the viewport
dpg.setup_dearpygui()
dpg.show_viewport()

# Run the main loop to keep the UI active
while dpg.is_dearpygui_running():
    dpg.render_dearpygui_frame()

# Destroy the context when finished
dpg.destroy_context()

```
<h3 align="center">↘️ example with decorate ↙️</a>
<br><br>
    
![example](https://github.com/user-attachments/assets/9f8873a4-2dc3-427d-9a12-b554300aedc3)

---

<h3 align="center">↙️ example without decorate ↘️</a></h3>

```python
import dpg_blur
from dpg_blur import WindowsWindowEffect, get_hwnd
import dearpygui.dearpygui as dpg

# Initialize DearPyGui context
dpg.create_context()

# Initialize the Windows window effect library
window_effect = WindowsWindowEffect()

# Function to apply the aero effect and rounded corners after UI is rendered
def after_init_ui():
    # Make the window background transparent
    window_effect.setAeroEffect(get_hwnd())
    # Apply rounded corners for Windows 11 (10px radius)
    window_effect.setRoundedCorners(get_hwnd(), 10) # IF YOU HAVE WINDOWS 10, THEN IT DOESN'T CHANGE ANYTHING.


# Set function to be called after rendering the UI
dpg.set_frame_callback(20, after_init_ui)

# Create a viewport with transparent background and no decoration (clear_color=[0, 0, 0, 0])
dpg.create_viewport(title="Example", decorated=False, clear_color=[0, 0, 0, 0], height=100, width=100)

# Setup and display the viewport
dpg.setup_dearpygui()
dpg.show_viewport()

# Run the main loop to keep the UI active
while dpg.is_dearpygui_running():
    dpg.render_dearpygui_frame()

# Destroy the context when finished
dpg.destroy_context()

```
<h3 align="center">↘️ example without decorate [win 11] ↙️</a>
<br><br> 

![example](https://github.com/user-attachments/assets/8a3a3865-79f5-4ee2-a845-4a74f6b78430)

<h3 align="center">---------------------------</a>

<br>

![example](https://github.com/user-attachments/assets/5f75914e-8c53-4ade-b58e-40745f3a6d9f)

<h3 align="center">↗️ example without decorate [win 10] ↖️<br>or without: 'window_effect.setRoundedCorners(get_hwnd(),10)'</a>

<br><br><br><br>
<h6 align="center">v. 1.1 <br> Made with 💟 by Agzes</h6>

