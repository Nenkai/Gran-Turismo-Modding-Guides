# X.1 Gran Turismo 5/6 - AppOpt System/Command
Both games allow command-line arguments to be provided to control the game at will.
One of them lets you stream game contents over your PC, without a volume required.

## 1. Requirements
- DEX FW Console with PS3 SDK installed (TMAPI) - Rebug D-REX 4.84 works.
- GT5/6
- PS3 Connected to PC via Ethernet
- Debug Converted EBOOT

## 2. Setup
Ensure that in Rebug Toolbox:
- Debug Menu Type = `DEX`
- QA Flag = `ON`

Ensure that in Debug Settings (XMB):
- Game Output Resolution: Set to whatever you want
- Release Check Mode: `Development Mode`
- Boot Mode: `System Software Mode`
- Network Settings for Debug: `Single Settings`

## 3. Setup Target Manager
* Start Target Manager.
* Right click `My Targets`, click `Add Target`.
* Put whatever in Name, select `Debugging Station`, press `Next`.
* In `IP address or host name`, put the IP of the PS3, then `Next` again, then `Finish`.
* Double click the target that was added to connect to it.
* Right click the target, go into `Properties`.
* In `Target`->`TM Properties`, look for `File Serving`, and `File server directory`. here, you want to put the parent directory of the game.
  Preferably the `USRDIR` directory, i.e: "C:\Games\BCES01893\USRDIR" where `BCES01893` is the game folder from /dev_hdd0/game/.
  
## 4. Setting up the game(s)
* The `USRDIR` folder should contain an extracted game contents folder containing the FULL game data, both GT.VOL and PDIPFS into one. 
Extract `GT.VOL` in one folder, extract the `PDIPFS` into another, then all extracted PDIPFS contents should go into the extracted GT.VOL folder. Name this folder `EXTRACTED`.

Important: Drag all files from where `USRDIR` is (i.e `TROPDIR`, `PARAM.SFO`) into `USRDIR`, create `PS3_GAME`in `USRDIR`, drag the `PARAM.SFO` there. It's weird but yeah.
In the end, you should end up with something like:
```
\ *
 \ BCES00569
  \- LICDIR
  \- TROPDIR
  \- USRDIR (which is /app_home)
    \- EXTRACTED (extracted game contents)
      \- advertise
  	  \- car
  	  \- carsound
  	  \- character
  	  \- ...
    \- LICDIR
    \- PS3_GAME
      | - PARAM.SFO
    \- TROPDIR
    |- EBOOT.BIN
  |- ...
```
## 5. Booting the game
* Right click the target in Target Manager, set Reset Mode to `Debug Mode`, then click `Reset`.
* Right click the target again, click "Load and Run Executable".
* At the bottom, in Command-line parameters, set: `fsroot=EXTRACTED`.
* Make sure only `Clear console output streams` is checked.
* Check only `Load from device`, select `/app_home`. Navigate to the game's folder, in USRDIR, then open it.

Game should now boot.

## 6. RPCS3
In the RPCS3 directory, create `app_home/`, paste your EXTRACTED folder there, then Boot RPCS3 as such with `cmd`:
```
rpcs3.exe <path to EBOOT> fsroot:EXTRACTED
```
## 7. Notes
TODO
