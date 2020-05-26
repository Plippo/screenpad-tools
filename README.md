# screenpad-tools
This repository contains a very simple script to control the brightness of the ASUS Screenpad Plus on the ASUS ZenBook Duo laptops.

To install it:
1. Install the [patched kernel module using dkms, as described here](https://github.com/Plippo/asus-wmi-screenpad) (for kernel 5.4)
2. It is important that you have added the line `sudo chmod a+w '/sys/class/leds/asus::screenpad/brightness'` to your `/etc/rc.local` file so that you can use the script without sudo.
3. download the script to your /usr/bin folder and make it executable:
   ```
   cd /usr/bin
   sudo wget 'https://raw.githubusercontent.com/Plippo/screenpad-tools/master/screenpad'
   sudo chmod a+x screenpad
   ```
   Now it is ready to use.
4. To control the brightness of your ScreenPad Plus, simple call:
   - `screenpad X` where X is a value between 1 and 9 to change the brightness (1 is darkest, 9 is brightest)
   - `screenpad 0` to turn the ScreenPad off (to turn it back on, just set the brightness using the command above)
   - `screenpad up` to increase the brightness one step
   - `screenpad down` to decrease the brightness one step
   - `screenpad toggle` to toggle the ScreenPad between on and off.
5. To facilitate using the script, add it to shortcut keys using the means of your desktop environment. E.g. GNOME has a tool to set shortcuts under Settings > Shortcut. Add a new command and set the shortcut you like. For instance, I set Windows+F4 to `/usr/bin/screenpad down` to decrease the brightness and Windows+F5 to `/usr/bin/screenpad up` to increase it. So just as you control the brightness of the main screen using Fn+F4/F5 you can now control the brightness of the ScreenPad using Windows+F4/F5. I also set the key next to the On/Off key to `screenpad toggle` so I can turn it on and off using that key, just like under windows.
