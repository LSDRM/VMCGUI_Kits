List of available kits for [VMCGUI](https://github.com/LSDRM/VMCGUI)
===============

Arduino based
----------
No arduino based kit has been developed yet.

Customized
----------
- [DualPressure - Thermocouple / through UART protocol](https://github.com/LSDRM/DualPressure-Thermocouple_forVMCGUI) : A DAQ board embeding two pressure sensors and one thermocouple. Developed by @B137P107

Raspberry Pi based
----------
No raspberry pi based kit has been developed yet.

Modules
----------
- [USB to UART bridge](https://github.com/LSDRM/USBtoUART-module_forVMCGUI) : To allow a computer the communicate through an UART communication line, via its USB port. Developed by @B137P107

Make your own kit
=============
This repository include a _#BlankKit.py_ file which is a base to start making your own kit, working with VMCGUI. Making your own kit requires a bit of electronical knowledge, especially if you want to do it by making your own DAQ board (i.e. without an Arduino or other ready-to-use DAQ board). Creating a new kit implies software and hardware development, the both parts are described below.

Software development
-----------
You should only need to make a python kit file from the _#BlankKit.py_, without modifying any file from the source code of VMCGUI. The latter file need to be renamed with the name you want to give it, and placed in the "APP/Kits" folder of the VMCGUI repository. Note that the _#_ right before the name of your file set this kit as inactive, so  VMCGUI will ignore it.

At the top of your kit file, you should find the imported packages. This is where you can call new packages for your application. For example, you can call `import pyfirmata` if you know your kit is an Arduino-based one using an USB connection.

The first method of the main class contained in the kit file is the `__init__` one. In this class, you should find parameters for your kit as described below :
- `self.setWindowTitle()` : Put between the brackets the title of the window for your kit in string format.
- `self.prefix` : This parameter take a string, which gonna be placed right before the default name of the recorded files.
- `self.closeStartWindowOnLaunch` : Is set to `True` by default to prevent opening multiple times the same Kit Window, which risks to create conflict between multiple windows calling the same connection port.
- `self.graphTitle` : Is a list of strings containing the name of each sensor present with the DAQ board.
- `self.sensorsNumber` : Shall not be modified since it need to correspond the number of sensors name in `self.graphTitle`.
- `self.GPIOsNumber` : Take the number of accessible GPIOs on the DAQ board.

Hardware development
-----------
### Arduino

### Customized

### Raspberry Pi
