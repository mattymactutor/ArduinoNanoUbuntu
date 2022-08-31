# ArduinoNanoUbuntu

Run the following
```
sudo dmesg -w
```

If you see something like this, then some other program is grabbing the Nano as it is plugged in. In this case, it is BRLTTY Screen Driver. Apparently this is for an Accessibility option for a braile reader and we do not need it.
```
[13689.575932] usb 3-2: New USB device found, idVendor=1a86, idProduct=7523, bcdDevice= 2.54
[13689.575936] usb 3-2: New USB device strings: Mfr=0, Product=2, SerialNumber=0
[13689.575938] usb 3-2: Product: USB2.0-Ser!
[13689.598429] usbcore: registered new interface driver usbserial_generic
[13689.598437] usbserial: USB Serial support registered for generic
[13689.599586] usbcore: registered new interface driver ch341
[13689.599594] usbserial: USB Serial support registered for ch341-uart
[13689.599607] ch341 3-2:1.0: ch341-uart converter detected
[13689.605004] ch341-uart ttyUSB0: break control not supported, using simulated break
[13689.605065] usb 3-2: ch341-uart converter now attached to ttyUSB0
[13689.614087] input: PC Speaker as /devices/platform/pcspkr/input/input38
[13690.130893] input: BRLTTY 6.4 Linux Screen Driver Keyboard as /devices/virtual/input/input39
[13690.134914] usb 3-2: usbfs: interface 0 claimed by ch341 while 'brltty' sets config #1
[13690.137014] ch341-uart ttyUSB0: ch341-uart converter now disconnected from ttyUSB0
[13690.137029] ch341 3-2:1.0: device disconnected
```

Remove BRLTTY
```
sudo apt remove brltty
```

Restart
```
sudo reboot now
```
