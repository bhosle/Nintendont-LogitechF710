### Fork of revvv/Nintendont-XBOX360 to support Logitech F710
* Recompiled by replacing XBOX360 VID:PID with Logitech's
* Rotated revvv's keymap for face button clockwise for my personal preference
* Working: Analog triggers
* NOT Working: Vibration. Tried all EndpointOut values from 1-8

Original README below

### Nintendont with XBOX360 controller support
* Only XBOX360 **wired version** is supported (VID=0x045e, PID=0x028e)
* You control player 1.
* Tested on Wii with Super Mario Sunshine on SD card.
* If the button layout is not perfect, try _L+Back_ to turn buttons quarter clockwise. (Nintendont feature.)

### HOWTO ###
* Connect your XBOX360 controller then start Nintendont-XBOX360. (Order is optional.)
* The XBOX360 LED 1 should now light up and the gamepad should react.<br>
  If you start a game the WiiMote LED says player 2.
* If your controller doesn't work try one of these options:
    1. Restart Nintendont-XBOX360 or your Wii.
    2. Replug your controller.
    3. Plug in your controller after you have started a game. 
    4. If it is still not working, try my USB gamepad tester [RetrodeTest](https://github.com/revvv/snes9xgx-retrode/releases/download/0.5/RetrodeTest-0.2.zip)
    to check if your Gamepad works at all.
    5. Set `EndpointOut=0` in`/controller/045e_028e.ini`. This will disable rumble and LED will flash.<br>
    Also use this settings if your Wii crashes. (Rare crashes are normal, though.)
  
### Turn on LED and rumble ###
* If the LED keeps flashing, this means that the LED cannot be set and also rumble will not work.
  Try to set `EndpointOut=2` in [/controller/045e_028e.ini](https://github.com/revvv/Nintendont-XBOX360/blob/master/controllerconfigs/045e_028e.ini).<br>
  The default is `EndpointOut=1` which is surprisingly correct for my controller ;-)<br>
  There are controllers which are not compatible with these settings. You could try the values 1-8.<br>
  Maybe check `lsusb -v -d 045e:028e` and grep for `OUT`. [Example output](https://gist.github.com/rombert/6902ab691e12ab478e31)

### Debugging ###
* Enable _Debugger_ and _Log_ in Nintendont-XBOX360 settings.
* Check log file `/ndebug.log`.
* The log file is not always written: Best practice is to start a game, then plug in your controller, then quit.

#### Download ###
* [Release](https://github.com/revvv/Nintendont-XBOX360/releases/)
* Unpack it to your SD card.
* Put games in folder `/games`
* *Optional:* Configure button layout in [/controller/045e_028e.ini](https://github.com/revvv/Nintendont-XBOX360/blob/master/controllerconfigs/045e_028e.ini).<br>
  __NEW:__ Fixed XBOX360 rumble for vWii<br>
  __NEW:__ Support 3rd party WiiMote + Nunchuk (labeled with "NEW2in1" and "Motion plus", distributed by Haiwai Consulting/Tiger-Zhou UG)
  
### Compile
Get these versions: devkitppc r29-1, devkitarm r47 and libogc 1.8.16 and execute _make_. 

### Disclaimer
This software comes without any warranty. I am not responsible for any damage to your devices. Please make backups!

