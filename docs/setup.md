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

Now, open SteamVR and wait for the default area to load.
Right now, only SteamVR works as the OpenXR runtime, due to a bug in the Oculus one that prevents input from passing to the game.
To check you have the right runtime, click the hamburger menu on the SteamVR status window and click settings.
From there, you need to enable advanced settings and go to the developer tab.
If the active OpenXR runtime is not SteamVR, click the button to switch it.

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

Open the now playing panel for SteamVR from in the headset. 
Click application-specific video settings.
Chose Battlefront.

This is often hit-or-miss, and may require multiple attempts.
Once you are able to see the settings, adjust the FOV slider until the VR eyes align.
Do not worry about being extremely zoomed in, this will be fixed in a later step.
Just make sure the alignment is correct.
Once it is, close Battlefront completely. You may leave SteamVR open.

Open the installation folder of Battlefront in File Explorer.
Open the file named `config.ini` with notepad.
Add the line `ManualFOV = 1;` with **proper indentation.**
Save the file and Open Battlefront one final time.

Launch the mod again.
Navigate to the video settings. 
Remember to use your controllers, the grip buttons are LB and RB.
Adjust the FOV slider to correct the extreme zoom in.
Once you are happy, remeber the value the slider is set to.

Open `config.ini` again and remove the line you added.
Change the `FOVOverride` value to the number from the FOV slider in the game settings.
Save the file.

Return to Battlefront and press the `HOME` key.
This should apply the FOV change.
If forever reason it does not, you may have to restart the mod and/or game.
The mod can be restarted by pressing the `END` key and lauching like normal again.

You may still notice some distortion, this is due to the FOV slider in-game only displaying whole numbers.
You can fix this by changing the value in `config.ini` in small increments and pressing the HOME key to apply the changes.
