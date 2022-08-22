# LinusTrinus

TrinusVR screen streaming server for Linux

## Available modes
#### Devices
- Mouse
- Steamvr
#### Screen capture
- ffmped
- xwd

## Dependencies

* [ffmpeg](https://command-not-found.com/ffmpeg)
* [xwininfo](https://command-not-found.com/xwininfo)
* [xwd](https://command-not-found.com/xwd)
* Python3 / Pypy3
* Python packages:
    * [wand](https://pypi.org/project/Wand/)
    * [evdev](https://pypi.org/project/evdev/) (optional)
* [TrinusVR](https://www.trinusvirtualreality.com/) Android client (tested on 2.2.1)

## Running

1. Start the TrinusVR Android client and configure it.
2. Press the start button in the TrinusVR Android client.
3. Run LinuxTrinus: `python3 main.py`

Detailed installation instructions in [INSTALL.md](INSTALL.md).

## Solution for Xiaomi and other devices

### Black screen
1. Edit the "width" and "height" parameters in the frame_generator/ffmpeg double_fg.py or ffmpeg_fg.py file to the monitor resolution.

### Phone/head too big/small. Lens correction - it renders both eyes squeezed on the bottom half of the screen.
1. Install wine or use windows
2. Install Trinus for windows on wine or windows (version for Google Cardboard)
3. Start Trinus (cd $PATH_TO_TRINUS && wine TGServer.exe)
4. Press "Start" in program and press start "trinus" on android, then activate this program.
5. When will be connect program and device you can change "Head mount" in top "Main".
6. Exit Trinus
7. Start LinusTrinus on Linux and enjoy

### Capture windows other than SteamVR
1. Enter to terminal:
xwininfo | grep "Window id" | sed "s/.* \\"/\\"/"
2. Click on the window you want to capture.
3. Edit parametr window_id = self.find_window_id("SteamVR Compositor") in file frame_generator/xwd_fg.py

## Thanks

* [r57zone](https://github.com/r57zone/OpenVR-OpenTrack) - for good example
* [TrinusVR team](https://www.trinusvirtualreality.com/) - for android client
