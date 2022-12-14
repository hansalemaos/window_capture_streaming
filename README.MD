### Grab screenshots from a specific window and process them right away

```python
pip install window-capture-streaming

# If you get the following error during the installation
#       ModuleNotFoundError: No module named 'win32.distutils.command'
#       [end of output]
# 
#   note: This error originates from a subprocess, and is likely not a problem with pip.
# error: subprocess-exited-with-error
# 
# Try this:

pip install window-capture-streaming --no-deps
pip install keyboard
pip install numpy
pip install opencv_python
pip install pandas
pip install a_cv2_easy_resize
pip install pywin32


from window_capture_streaming import WindowIterCapture
import re
import cv2
capt = WindowIterCapture(
    hwnd=None,
    window_text=re.compile(r".*bluestacks.*", flags=re.IGNORECASE),
    show_capture_keys="ctrl+alt+z",  # starts cv2.imshow() - can be enabled/disabled by pressing ctrl+alt+z
    show_fps_keys="ctrl+alt+f",  # show the fps rate - can be enabled/disabled by pressing ctrl+alt+f
    kill_screencap_keys="ctrl+alt+x",  # kills the capture process
)

for screen_shot in capt.get_screenshot(
    sleeptime=None,
    resize_width=None,
    resize_height=None,
    resize_percent=None,
    interpolation=cv2.INTER_AREA,
):
    pass
    # print('do some stuff here')


```

