# Mylens
## Setting Up a Mouse Button Shortcut to Execute a Script in Ubuntu

Follow these steps to bind an auxiliary mouse button to a script on Ubuntu.

### 1. Identify the Mouse Button

1. Open a terminal and run the following command:
    ```
    xev | grep button
    ```
2. Click the button inside the window. The terminal will output something like this:
    ```
    state 0x10, button 8, same_screen YES
    ```
    Note the button number `button 8`.

### 2. Install `xbindkeys` and `xautomation`

1. Install the necessary packages by running the following command in the terminal
    ```
    sudo apt-get install xbindkeys xautomation
    ```
### 3. Create an `xbindkeys` Configuration File

1. Create the default configuration file if it doesn't exist:
    ```
    xbindkeys --defaults > ~/.xbindkeysrc
    ```
2. Open the configuration file for editing:
    ```
    nano ~/.xbindkeysrc
    ```
3. Add a new binding at the end of the file, replacing `/path/to/your/script.sh` with the path to your script, and `b:8` with the identified button number:
    ```
    "sh /path/to/your/script.sh"
        b:8
    ```
### 4. Test the configuration:
    ```
    xbindkeys
    ```
