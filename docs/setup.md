---
layout: default
---
# Setup

This guide will show you how to get BF2VR up and running. A video guide can be found [here](https://youtu.be/KxQb4e2cLDc).

## Download the mod

To access the mod, you will need to join my [Discord server](https://discord.com/invite/mrKYwzd3N4). 
Once you have read the rules, go to the **#specs** channel and list your computer's hardware.
After that, you can go to **#role-apply** and click the 🧪 reaction to gain access to the mod.
Finally, download the latest zip file from **#releases** and extract it to a known location.
This is where you will find all future copies of the mod.

## Install ViGEm

BF2VR uses the Virtual Gamepad Emulation Framework (ViGEm) to handle controller input. 
To use it, you need to go to their [releases page](https://github.com/ViGEm/ViGEmBus/releases) and download the latest exe from the assets list.
Follow the setup instructions.

## Whitelist the folder

Windows Defender (and other antiviruses) may try to flag the mod as harmful.
This is because it injects code into Battlefront, similar to how some malware will inject code into sensitive applications.
To solve this, open Windows Defender (and/or your antivirus) and find the exclusions list.
In windows defender this is under `Virus & threat protection` > `Virus & threat protection settings` > `Exclusions`.
Add the location of the mod folder you downloaded and extracted.

## Install the mod

First, you will need to find the location where Battlefront is installed.
You can often find this by going into the properties of the game in your launcher.
Copy this path to your clipboard.

Open `Launcher.exe` and click `F10` on your keyboard.
Click enter to acknowledge the message.
A small and annoying file picker will appear, but you can paste the path you copied earlier into the `Folder` field.
Once you do so, the mod will install.


## First time setup

Now, open SteamVR or Oculus and wait for the default area to load.

Next, you can launch Battlefront. Remeber, pirated copies don't work.
Go to the settings menu and make sure these settings are applied:

* Fullscreen mode: Borderless
* DirectX 12: Disabled
* Vertical Sync: Disabled
* Lens Distortion: Disabled
* TAA Quality: High

Now return to the main menu.

Back in the mod folder, open `Launcher.exe` again. 
This time, press enter.
The Battlefront window will resize and a console will show up.
The console will tell you that is is configuring, and that the game will need to be restarted.
Close Battlefront completely and open it again.

Once Battlefront is at the menu again, open `Launcher.exe` and launch the mod again.
If all goes well, you will see the game in 6DOF vr and will be able to use your controllers as input. 
If they don't work, make sure you have all physical controllers disconnected.
Have fun playing!

If you experience crosseye or eye alignment issues, continue to the next section.

## Fixing crosseye issues

Once the mod is running, you will find a file called `config.ini` in the Battlefront folder.

There are three values you can change, each for a different potential issue. By default, the configuration will have nothing in it. If you want to override some values, start by pasting this into the file:

```
[ Core ]
```

You can then continue to any or all of the following sections.

### Distortion when tilting head left or right
The aspect ratio of the game camera has an important impact on how the image is projected to the VR screens.

The mod tries to find the best value supplied to it by OpenXR, but in some cases (like Virtual Desktop), the values are incorrect.

You can change this value by pasting the following on a new line in the configuration (including the indentation):

```
	EyeAspectRatio = 0.89;
```

You can change the `0.89` to whatever value works for you. You can find some valuable info about your headset in the [HMD Geometry Database](https://risa2000.github.io/hmdgdb/).

### Zoomed in or zoomed out (FOV)
The FOV of the game must match perfectly with the VR to prevent motion sickness.

Like the aspect ratio setting in the above section, it is set to the reccomeded values but you can
adjust it if it doesn't work for you.

The format for this parameter is like this:

```
	FOVOverride = 89;
```

### Crosseye or misaligned vision
This one was a mystery for a while. To have good stereo convergence, the eyes have to be aligned properly. The mod now does a best guess, but here is how to set it yourself.

Keep in mind that zero may be a good value, not just higher numbers. For example, Virtual Desktop on the Quest 2 does some correction already, and you won't need any adjustment of the eye convergence.

This value defaults to around 200 on the Quest 2, as a reference. Keep in mind this is in pixels.

```
	EyeConvergenceOverride = 0;
```
