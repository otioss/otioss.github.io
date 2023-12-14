---
title: "Front-Mounted LCD Panel with Firmware Upgrade for Ender 3 V2"
date: '2021-02-07'
---


Creality ditched matrix LCD in favor of a fancy <del>colorful</del> all-blue LCD in **Ender 3 V2**. Except they forgot to develop a decent firmware for it and they mounted it in the worst spot they could possibly find. Heaven knows how many times I have hit this display accidentally. Is it possible to design a better LCD panel to decrease printer's footprint and make it more compact? To find out, I wasted a few weekends to create this first otiose thing:

[![otioss-ender3-v2-7.jpg](https://i.postimg.cc/76Xt9Ss7/otioss-ender3-v2-7.jpg)]()

What you see is not an MK3S, it is the Ender 3 V2's stock LCD with a new cover, mount and firmware. Here is what I've done:

1. **CAD the Panel** (<span style="color:green">Completed</span>) : I used the infamous open source [FreeCAD](https://www.freecadweb.org/) to design the cover and the mount. This part was fun.
2. **Modify Marlin Firmware** (<span style="color:green">Completed</span>): This is the most challenging part. Why? Because Creality's LCD code is just awful and has no support for landscape layout. So I have to modify the code substantially to make this work. This part is not fun at all. I love coding but Creality's macabre DWIN code is just a nightmare.
3. **Modify Display's UI Elements** (<span style="color:green">Completed</span>): The LCD (made by DWIN) has all the UI elements stored as low-res images in its local storage. These images had to be modified to fit in the new landscape layout.

[![otioss-ender3-v2-2.jpg](https://i.postimg.cc/jq9QNzZk/otioss-ender3-v2-2.jpg)]()

There were several design principles I tried to adhere to:

- **No Support**: I don't like supports. They waste filament and make the print ugly. So I made sure no support is needed for printing this panel.
- **Print Time < 4 Hours**: I did my best keep the print time under 4 hours. A lot of upgrades these days take all day and all night to print and waste a lot of filament.
- **Minimalistic Design**: No unnecessary features. Just a simple panel to conserve filament.
- **Easy to Assemble**: Well, I probably failed here. But let's see. Hope the following instructions make it easier.


## What You'll Need ##
1. lots of patience.
2. _<span style="color:brown">M3 x 8mm</span>_ or _<span style="color:brown">M4 x 8mm</span>_  screw (1x):  You can use the same screw and t-nut that is used to mount the stock display.
3. _<span style="color:brown">T-nut</span>_ (1x): Use the stock t-nut.
4. _<span style="color:brown">M3 x 20mm</span>_ screw (4x)
5. _<span style="color:brown">M3</span>_ nut (4x)
6. _<span style="color:brown">M5</span>_ screw (2x)

Note: This design assumes you are using the printer's stock feet (~12mm tall). If you are using some customized damping feet that lifts your printer higher than the stock ones, the panel might end up hanging above the table surface.

Once you have everything, grab some munchies (gummy bear?) and read on.

## How to Print ##
First, download all the files from [thingiverse](https://www.thingiverse.com/thing:4753473). Open slicer of your choice. Cura, Slic3r, Prusaslicer are all fine. I recommend to print in PETG or ABS with at least 40% infill. PLA could work as well but I am not sure if is strong enough for this project. Feel free to test PLA and let me know about result. I increased the print speed to 60mm/s without sacrificing quality much. Lay down the STL's according to the pictures below and you won't need any _support_.

**lcd-cover.stl** (print time ~ 1 hour 40 minutes):
[![lcd-cover-print.png](https://i.postimg.cc/43GP2cKQ/lcd-cover-print.png)]()

**lcd-mount.stl** (print time ~ 2 hours 10 minutes):
[![lcd-mount-print.jpg](https://i.postimg.cc/sDc5fL17/lcd-mount-print.jpg)]()

**spacer.stl** (print time ~ 8 minutes for all four spacers):
[![spacer-print.jpg](https://i.postimg.cc/sDQqWpdn/spacer-print.jpg)]()

**knob** (Optional)
You can use the stock knob, this [one](https://www.thingiverse.com/thing:4636604), this [one](https://www.thingiverse.com/thing:4640582) or any other knob.
[![ender3-v2-knob.jpg](https://i.postimg.cc/tCVrv8hd/ender3-v2-knob.jpg)]()


## Assembly Instructions ##

1. First, you need to tear down the stock LCD panel. Remove the the knob and all the screws. [Here](https://www.youtube.com/watch?v=Jswzrh2_ekk) is a video to help you. The only thing we need is the PCB (set it aside for now): 
[![ender3-v2-lcd-pcb.jpg](https://i.postimg.cc/T1kGM8g9/ender3-v2-lcd-pcb.jpg)]()

2. Take the lcd-mount and insert all four M3 nuts in the prepared slots according to picture below. I've designed them to be tight to make sure the nuts won't fall later during assembly. You might have to press them firmly to make them go all the way in: 

[![ender-3-v2-mount-nuts.jpg](https://i.postimg.cc/gjdYpkf3/ender-3-v2-mount-nuts.jpg)]()

3. Remove the plastic cap from the right aluminum extrusion. I highly recommend to remove the stock drawer (watch this [video](https://www.youtube.com/watch?v=-uW8lKUrjRk)). If you decide to leave it as it is, you could try to remove the drawer's knob and see if you can proceed with the assembly. Please let me know if this works.

[![ender3-v2-extrusion.jpg](https://i.postimg.cc/9X71LPps/ender3-v2-extrusion.jpg)]()

4. Now we try to attach the left side of the mount to the printer. For this we use one T-nut and an M3 x 8mm screw. The left side of the mount gets attached to the bottom of the middle aluminum extrusion. You might have to lift up the printer a bit. I did a little trick by moving the printer to the edge of my table (be careful not to drop the printer) and work under it. I am not a big fan of T-nut screws. They are tricky and annoying. You have two options: (a) insert the T-nut at the bottom of printer and then screw: 

[![ender3-v2-under.jpg](https://i.postimg.cc/VNCsC7yL/ender3-v2-under.jpg)]()

or (b) insert the T-nut and screw in the mount and then attach it to the printer:

[![ender-3-v2-mount-t-nut.jpg](https://i.postimg.cc/RC8PPG2z/ender-3-v2-mount-t-nut.jpg)]()

This is kind of important: Make sure the left side of the mount is **aligned** with the front of the right aluminum extrusion (where the right side of the mount will be attached to later on). Then tighten the screw under the printer:

[![front-mount-left-side.jpg](https://i.postimg.cc/VN97NCfZ/front-mount-left-side.jpg)]()

Ok, the left side of the mount is finished. Now for the right side, use two M5 screws. Actually I designed three holes for three M5 screws but that is a bit of overkill. Two is perfectly adequate. 

[![ender3-v2-front-mount.jpg](https://i.postimg.cc/mr2KHjP1/ender3-v2-front-mount.jpg)]()

Very well, you've just installed the mount successfully. Now let's attach the lcd-cover to the lcd-mount. Pick up the PCB, put the cover on top of it and insert all four M3 x 20mm screws:

[![ender3-v2-panel-horizontal.jpg](https://i.postimg.cc/W46TLVzR/ender3-v2-panel-horizontal.jpg)]()

Insert all four spacers:

[![ender3-v2-back-display-pcb.jpg](https://i.postimg.cc/XJgQfHJ6/ender3-v2-back-display-pcb.jpg)]()

Carefully, install the cover+pcb in a slow tilt motion according to picture below. Move it slowly to prevent spacers from falling. First connect the bottom two screws and then slowly tilt the screen (maybe hold the upper two spacers with your hand to make sure they don't fall) and attach the top two screws: 

[![ender3-v2-font-panel-installation.jpg](https://i.postimg.cc/bN1gK75P/ender3-v2-font-panel-installation.jpg)]()

Once you are sure all screws and spacers are placed properly, tighten all four screws. please  <span style="color:red">DO NOT over-tighten</span> the screws as it might bend the cover. Just screw it tight enough so that the cover and LCD are attached to the mount firmly:

[![ender-3-v2-font-mounted-panel-landscape.jpg](https://i.postimg.cc/Fs2tZXLQ/ender-3-v2-font-mounted-panel-landscape.jpg)]()

Now insert the knob (just press it). Plug the LCD cable and turn on the printer:

[![otioss-ender3-v2-6.jpg](https://i.postimg.cc/rw8Hgyw3/otioss-ender3-v2-6.jpg)]()

Congratulations! You successfully finished the installation. 
[![otioss-ender3-v2-4.jpg](https://i.postimg.cc/x81ktbBq/otioss-ender3-v2-4.jpg)]()

Now it is time to install the firmware. 

## Firmware ##

_Ender 3 V2_ uses the open source [Marlin](https://marlinfw.org/) firmware. The LCD is controlled by DWIN LCD code (originally written by Creality) within Marlin firmware. There is no support for landscape layout in DWIN code so I decided to implement this feature myself alongside some other improvements:

[![otioss-firmware-ender3-v2.jpg](https://i.postimg.cc/DyRHrZ1N/otioss-firmware-ender3-v2.jpg)]()

I have compiled two variants of the firmware which you can download below. However I recommend you to configure and compile the firmware yourself instead of using these binary files: 

1. [otioss-firmware-bltouch.bin](https://archive.org/download/otioss-firmware-bltouch/otioss-firmware-bltouch.bin): For BLTouch users (tested on my machine). Don't forget to adjust your e-step and other settings after flashing firmware.
2. [otioss-firmware-non-bltouch.bin](https://archive.org/download/otioss-firmware-bltouch/otioss-firmware-non-bltouch.bin): For Non-BLTouch users (Not tested. Use with Caution. Please report your findings)

In what follows, I will show you how to configure and compile this customized firmware for your Ender 3 V2 3D printer. If you are a beginner with no experience regarding configuring and compiling Marlin, do not worry. With a bit of patience and experimentation, you can compile and install this firmware.

**Install Git + Visual Studio Code + Platform IO**. First make sure [Git](https://www.atlassian.com/git/tutorials/install-git) is installed on your system. Then install [Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) and then install [PlatformIO](https://marlinfw.org/docs/basics/install_platformio_vscode.html) within Visual Studio Code.

[![vscode-platformio.jpg](https://i.postimg.cc/Xv9qRvkZ/vscode-platformio.jpg)]()

**Download the Firmware**. The firmware's code is available on my [github](https://github.com/otioss/Marlin). Get a copy by issuing <span style="color:brown">git clone</span>  command: 

```git clone https://github.com/otioss/Marlin.git```

**Opening Marlin**: In Visual Studio Code go to <span style="color:brown">file > open folder</span> and select the Marlin folder you just <del>downloaded</del> cloned. After that, click on <span style="color:brown">2.0.x</span> branch icon at the bottom left of the screen:

[![2x-visual.jpg](https://i.postimg.cc/JzPkLy5d/2x-visual.jpg)]()

and from drop-down menu select <span style="color:brown">origin/bugfix-2.0.x</span>:
[![bugfix2.jpg](https://i.postimg.cc/CM2BX53N/bugfix2.jpg)]()

Now you can see the branch icon at the bottom left of the screen has changed to <span style="color:brown">bugfix-2.0.x</span>:

[![bugfix-visual-studio.jpg](https://i.postimg.cc/yxBzTyrf/bugfix-visual-studio.jpg)]()


**Configuring Marlin**: This is the most important step. There are two main configuration files within Marlin firmware: 

- `Marlin\Configuration.h`
- `Marlin\Configuration_adv.h`

There are no fixed settings. Each printer is different and depending on your modifications/upgrades (ABL, custom extruder, all-metal hotend, etc) you need to adjust the settings according to your machine and preference. Marlin website has a [definitive guide](https://marlinfw.org/docs/configuration/configuration.html) about these two files that I highly recommend. Generally, the configuration falls in one of the following categories:

- **BLTouch Users**: If you have BLTouch installed on your Ender 3 V2, you can use the default configuration that comes with my Marlin repo you downloaded above. There might be some differences between my setup and yours. For example my e-step is 400 (for BMG extruder) so make sure you change it if you use stock or a different extruder (look for <span style="color:brown">DEFAULT_AXIS_STEPS_PER_UNIT</span>  line). Actually you can change many of these settings with G-code commands later.
 

- **Non-BLTouch Users**: Marlin developers provide [configuration files](https://github.com/MarlinFirmware/Configurations/tree/import-2.0.x/config/examples/Creality/Ender-3%20V2) suitable for stock Ender 3 V2. This is the best course of action for beginners. You can pretty much copy the content the [Configuartion.h](https://raw.githubusercontent.com/MarlinFirmware/Configurations/bugfix-2.0.x/config/examples/Creality/Ender-3%20V2/Configuration.h) and [Configuration_adv.h](https://raw.githubusercontent.com/MarlinFirmware/Configurations/bugfix-2.0.x/config/examples/Creality/Ender-3%20V2/Configuration_adv.h) and replace them with the ones in Visual Studio Code. Read the settings again to make sure they match your printer. 

**Platform.ini**: In Visual Studio Code, navigate to <span style="color:brown">platform_ini</span>, locate and set 

```default_envs = STM32F103RET6_creality```

 
**Board Model**: Navigate to <span style="color:brown">Marlin/Configuration.h</span> and find <span style="color:brown">#define MOTHERBOARD</span> line. If you use the default <span style="color:brown">V4.2.2</span> board that comes with majority of Ender 3 V2s, just set 
 
`#define MOTHERBOARD BOARD_CREALITY_V4`
 
If you use the newer <span style="color:brown">V4.2.7</span> board, set it to 
  
`#define MOTHERBOARD BOARD_CREALITY_V427`

**Enable Landscape Mode**: This is enabled by default in my firmware so you do not need to change it. To double check, head to <span style="color:brown">Marlin/src/lcd/dwin/dwin_lcd.h</span> and make sure <span style="color:brown">LCD_ROT</span> is set to <span style="color:brown">1</span>:

```#define LCD_ROT 1```

If in the future you want to revert to vertical portrait orientation, you can set it to <span style="color:brown">0</span>. Also make sure both <span style="color:brown">#define USE_STRING_HEADINGS</span> and <span style="color:brown">#define USE_STRING_TITLES</span> are uncommented in <span style="color:brown">Marlin/src/lcd/dwin/e3v2/dwin.cpp</span>.

Tip: For those who wish to mount the panel on the left side of the printer, I have added the <span style="color:brown">LCD_FLIP</span> option. By default it is <span style="color:brown">0</span> which means the display knob ends up on the right side. If you set it to <span style="color:brown">1</span> the screen is flipped upside down with knob on the left side. In the future, I plan to provide a mirrored version, suitable for mounting the display on the left side of the printer.


**Compilation**: Click the little check mark &#10003; button at the bottom of Visual Studio Code:

[![tick-visual-studio-1.jpg](https://i.postimg.cc/cLcJGwmp/tick-visual-studio-1.jpg)]()

The compilation starts hopefully you see a success message:

[![compile-success.jpg](https://i.postimg.cc/XNBgGt9N/compile-success.jpg)]()

**Locate the Firmware File**. The final compiled firmware is stored in a file with <span style="color:brown">.bin</span> extension. If you look at terminal window (screenshot above) , you can find the location of <span style="color:brown">.bin</span> file which is usually something like this: <span style="color:brown">.pio/build/STM32F103RET6_creality/firmware-{current date-time}.bin</span>. Using your file browser, navigate to that directory and copy the <span style="color:brown">.bin</span> file to a Micro SD Card.

[![filefolder-1.jpg](https://i.postimg.cc/g2MwfsX5/filefolder-1.jpg)]()


**Flash Firmware** Copy the <span style="color:brown">.bin</span> file to your Micro SD card. Make sure it is the only <span style="color:brown">.bin</span> file there with a new name (Visual Studio always produce files with unique names based on date/time). Insert the Micro SD card in your Ender 3 V2 printer and turn it on. You see black screen for a few seconds and then your printer boots with new firmware.


Congratulations! Hope everything goes smoothly for you. I recommend that you re-check your e-steps (e-step is shown in **status area** of the screen) and other settings before you start to print. If you have BLTouch, I recommend to run <span style="color:brown">Level Bed</span> and then <span style="color:brown">Store Settings</span> to create and save a new mesh of your bed. If you have any questions, don't hesitate to contact me. 

## Skinning the UI (Optional) ##

Now it's time to flash a new set of icons to the LCD's memory. The DWIN LCD has a Micro SD card slot at the back that can be used to flash icons and other media to the LCD's internal storage. The flashing procedure is a bit specific so please follow the instructions exactly as follows.

**Format your Micro SD Card**. The important thing is that your Micro SD card has to be formated in FAT32 with allocation size of 4096 (4K) bytes. It is very important the allocation size is 4K bytes. If not, the flashing won't work. Make sure the Micro SD card is empty and there are no files there. I recommend not to use a Micro SD Card with an astronomical capacity (e.g. 256GB). An 8GB or 16GB Micro SD Card is perfectly fine.

**Get the ICONS**: The icons and boot logo are available on my [github](https://github.com/otioss/Ender3v2-Configuration). Download the <span style="color:brown">DWIN_SET</span> folder.

**Flash Firmware**: Copy the <span style="color:brown">DWIN_SET</span> to your Micro SD Card. Insert the Micro SD card in the back of your LCD's Micro SD card slot and turn on the printer. You'll see a blue screen for a few seconds followed by an orange screen. When you see the orange screen it means the flashing is complete. Turn off the printer, take out the Micro SD card and then turn the printer back on. If everything was done correctly, you should see the new icons:

[![IMG-3152.jpg](https://i.postimg.cc/HWSCp4wq/IMG-3152.jpg)]()

Please note that this is still a work in progress. I plan to add many more features to this firmware in the future. If you like my work, please consider supporting my work on <a href="https://patreon.com/otioss">Pateron</a>. 

The comment section of this website is not fully-developed yet. Please leave your comments on [thingiverse](https://www.thingiverse.com/thing:4753473) or contact me on <a href="https://twitter.com/otioss">Twitter</a>.


