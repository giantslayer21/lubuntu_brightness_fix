# FIX THE BRIGHTNESS iSSUE ON LUBUNTU (OR ANY LINUX DISTRO)
A bash script to fix the brightness issue in Lubuntu on Intel laptops. (This should probably work on any linux distro, given that it is an intel machine.)

## Backstory:

This script was created after much research on how to fix the brightness issue on lubuntu, and failing to find an easy to use, simple fix.
Hope it helps you.

There is a text file called 'brightness' in the following directory:
/sys/class/backlight/intel_backlight/
Changing the value stored in that file aparently changes the brightness of the system.

## Usage:

1. Save the brightness_control file in the /bin directory
2. Give it executable permission through the terminal using:
    `sudo chmod 755 brightness_control`
3. Now open the sudoers file to make the file execute without having to need sudo every time you use it:
    `sudo visudo /etc/sudoers`
4. Add the following lines at the end of the sudoers file:
    ```
    #the following commands can be run as sudo without giving password
    user_name ALL=(root) NOPASSWD: /bin/brightness_control
    ```
5. Save and exit. Now open the respective Shortcut Keys Application on your distro.
    * Add a new shortcut and pass the following commads to your preferred shortcuts:
      - To increase brightness: `sudo brightness_control +`
      - To decrease brightness: `sudo brightness_control -`
    Here's what I did. I just replaced the existing keys' associated commands with appropriate command from above

### Note: This script was designed to fix the brightness issue on machines running lubuntu, but it should run on any linux machine with intel.
### The commands can be used directly from the terminal too, and works the same way.
