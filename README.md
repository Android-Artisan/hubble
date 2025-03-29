# Hubble - A USB Recovery Tool for devices based on Exynos9830

## Why?
 - Why not?
 - I don't want people to be paying to unbrick their devices

## Platform preperation

### Linux

- Open or create ```/etc/udev/rules.d/51-android.rules``` as **root**
- Add the following lines to the file
```
# Samsung Exynos USB Boot Mode
SUBSYSTEM=="usb", ATTR{idVendor}=="04e8", ATTR{idProduct}=="1234", MODE="0660", GROUP="dialout"
```
- Save the file and exit your editor
- Run ```sudo udevadm control --reload && sudo udevadm trigger``` to reload UDEV rules
- You can now run the tool.

### Windows

- Uninstall any existing BootROM Drivers
- Install the ones provided by right clicking the inf and pressing install
- You can now run the tool.

## How do I use it?
 - Install required python packages via ```pip3 install -r requirements.txt```
 - Run the tool, pointing to your bootloader tar file via ```python3 hubble.py -b <PATH_TO_BL_TAR>```
 - Plug in your bricked phone
 - Let it run it's magic
 - Reflash the stock firmware

## Supported devices

 > [!Warning]
 > This tool is strictly for devices based on Exynos9830!

 - [ ] Means your device is most likely supported but not tested
 - [x] Means your device is supported and tested

>

 - [x] Samsung Galaxy S20 (x1s/lte)
 - [x] Samsung Galaxy S20 Ultra (z3s/lte)
 - [ ] Samsung Galaxy S20+ (y2s/lte)
 - [ ] Samsung Galaxy S20 FE (r8s)
 - [ ] Samsung Galaxy Note20 (c1s/lte)
 - [ ] Samsung Galaxy Note20 Ultra (c2s/lte)

## Credits
 - [VDavid003](https://github.com/vdavid003) ```Helped me get the BL2 split on the bootloader```
 - [gaitenis](https://xdaforums.com/m/gaitenis.13049039) ```Finding lk.bin split```
 - [halal-beef](https://github.com/halal-beef) ```Initial idea, writing the tool and getting most of the splits```
 - [BotchedRPR](https://github.com/BotchedRPR) ```Loads of support and bricked his S20 Ultra for testing splits, absolute legend```
