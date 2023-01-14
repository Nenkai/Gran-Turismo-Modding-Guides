# Gran-Turismo-5-6-Modding-Guides
Modding guides for PS3-era Gran Turismo.

## Prerequisites
* Understanding how Command Prompt/`cmd` works and openning it in a current openned folder.
* Windows, obviously.
* At least 30-40Gbs of space for each game that you want to mod.
* Modded Console or [RPCS3](https://rpcs3.net/).
* Knowing how to FTP inside your console.
* If modding GT6: [GT6 Mod Base](http://www.mediafire.com/folder/8d08of132m00y/GT6+Mod+Base) to use as base - extract it later on and use it to make your mod - **for 1.22/latest only.**

## Table of Contents
0. [Dealing with file unpacking/repacking, understanding PDIPFS](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/0.%20Understanding%20PDIPFS/Understanding_PDIPFS.md)
	1. [Unpacking](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/0.%20Understanding%20PDIPFS/Understanding_PDIPFS.md#unpacking)
	2. [Repacking](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/0.%20Understanding%20PDIPFS/Understanding_PDIPFS.md#packing)
	3. [Removing Files from the Game](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/0.%20Understanding%20PDIPFS/Understanding_PDIPFS.md#removing-files-from-the-game)
	4. [Advanced Notes](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/0.%20Understanding%20PDIPFS/Understanding_PDIPFS.md#technical-details-about-pdipfs-advanced)

1. Custom Events
	1. [Creating a Folder](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/1.%20Events/Creating_Folders.md)
		1. [(GT5) Creating a new Event Folder](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/1.%20Events/Creating_Folders.md#gt5-creating-a-new-event-folder)
		    * [Giving it a Title/Description](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/1.%20Events/Creating_Folders.md#gt5-folder-titledescription)
		2. [(GT6) Creating a new Event Folder](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/1.%20Events/Creating_Folders.md#gt6-creating-a-new-event-folder)
	2. [Creating an Event](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/1.%20Events/Creating_Events.md)
	3. [Creating an Event Image](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/1.%20Events/Creating_And_Event_Image.md)
		1. [GT5](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/1.%20Events/Creating_And_Event_Image.md#gt5)
		2. [GT6](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/1.%20Events/Creating_And_Event_Image.md#gt6)

2. [Image Editing](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/2.%20Image%20Editing/Image_Editing.md)
	1. [TXS3/.img Files](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/2.%20Image%20Editing/Image_Editing.md)
	2. [TXS3->Normal Image](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/2.%20Image%20Editing/Image_Editing.md#img-to-png)
	3. [Normal Image->TXS3](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/2.%20Image%20Editing/Image_Editing.md#pngjpgbmp-to-img)
	
3. [String/Text Editing](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/3.%20String%20Editing/String_Editing.md#stringtext-editing)
	1. [Understanding the RT2 localization system](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/3.%20String%20Editing/String_Editing.md#understanding-the-rt2-localization-system)
	2. [Editing Strings](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/3.%20String%20Editing/String_Editing.md#editing-strings)

4. [Sound Editing](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/4.%20Sound%20Editing/Sound_Editing.md)
	1. [Car Engine Sound Structure](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/4.%20Sound%20Editing/Sound_Editing.md#car-engine-sound-structure)
	2. [ESGX Sounds](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/4.%20Sound%20Editing/Sound_Editing.md#esgx-sounds)
	3. [AES Sounds (GT6)](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/4.%20Sound%20Editing/Sound_Editing.md#aes-sounds)
	4. Musics
	5. Playlist Editing

5. [SpecDB/Car Editing](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/5.%20SpecDB/SpecDB_Editing.md)
        1. [Decryption (GT6)](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/5.%20SpecDB/SpecDB_Editing.md#50-specdb---car-specifications)
	2. [Database Tables](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/5.%20SpecDB/SpecDB_Editing.md#2-tables)

6. [The Adhoc Script Language/System](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/6.%20Adhoc/Introduction.md)
	1. [Introduction](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/6.%20Adhoc/Introduction.md)
	2. [Editing Scripts](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/6.%20Adhoc/Scripts.md)
	3. [UI Editing](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/6.%20Adhoc/UI.md)
	4. [GPB Editing (Project Resources)](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/6.%20Adhoc/GPB_Resources.md)
7. Useful Resources
	1. [Optimal Modding Setup](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/X.%20Other/Optimal_Setup_For_Modding.md)
	2. [Command Line Arguments & FSRoot](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/X.%20Other/Command_Line_Arguments_FSRoot.md)

## Credits
- Nenkai#9075 - Base Guide
- TheAdmiester - All Sound Related Guides
