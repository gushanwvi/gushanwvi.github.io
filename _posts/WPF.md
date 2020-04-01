### Command Line

* [https://www.wpf-tutorial.com/wpf-application/command-line-parameters/](https://www.wpf-tutorial.com/wpf-application/command-line-parameters/)

### Exceptions

* [https://www.wpf-tutorial.com/wpf-application/handling-exceptions/](https://www.wpf-tutorial.com/wpf-application/handling-exceptions/)



### Important Window properties

The WPF Window class has a bunch of interesting attributes that you may set to control the look and behavior of your application window. Here's a short list of the most interesting ones:

**Icon** - Allows you to define the icon of the window, which is usually shown in the upper left corner, to the left of the window title.

**ResizeMode** - This controls whether and how the end-user can resize your window. The default is CanResize, which allows the user to resize the window like any other window, either by using the maximize/minimize buttons or by dragging one of the edges. CanMinimize will allow the user to minimize the window, but not to maximize it or drag it bigger or smaller. NoResize is the strictest one, where the maximize and minimize buttons are removed and the window can't be dragged bigger or smaller.

**ShowInTaskbar** - The default is true, but if you set it to false, your window won't be represented in the Windows taskbar. Useful for non-primary windows or for applications that should minimize to the tray.

**SizeToContent** - Decide if the Window should resize itself to automatically fit its content. The default is Manual, which means that the window doesn't automatically resize. Other options are Width, Height and WidthAndHeight, and each of them will automatically adjust the window size horizontally, vertically or both.

**Topmost** - The default is false, but if set to true, your Window will stay on top of other windows unless minimized. Only useful for special situations.

**WindowStartupLocation** - Controls the initial position of your window. The default is Manual, which means that the window will be initially positioned according to the Top and Left properties of your window. Other options are CenterOwner, which will position the window in the center of it's owner window, and CenterScreen, which will position the window in the center of the screen.

**WindowState** - Controls the initial window state. It can be either Normal, Maximized or Minimized. The default is Normal, which is what you should use unless you want your window to start either maximized or minimized.