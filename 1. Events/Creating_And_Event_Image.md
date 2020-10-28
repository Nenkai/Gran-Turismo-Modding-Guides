# Creating an Event/Folder Image

*To create an image refer to [Image Editing](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/2.%20Image%20Editing/Image_Editing.md)*.

Any event will still work without an image.

## GT5
Only GT5 folders can have images. 

The event images are located at `piece\flyer` and their dimensions are `860x360`. They must be named according to your event id file. 

If your event xml is `r1000.xml`, your image must sit there as `r1000.img`. 

## GT6
GT6 can have both folder and event images.

* Folder images are available if you are using a regular folder (non-mission etc.)
* Event images are available if you are using a non regular folder (missions, one-make, coffee break, license & endurance).

Locations:
* Regular folder images - `piece\gt6\event_flyer` - DXT1-3 - Must be named according to the folder name.
* Event images - `piece\gt6\event_img` - DXT1-3 - 320x452 - Must be named according to the folder name.

Additionally the [Event Generator](https://github.com/Nenkai/GTEventGenerator) supports outputting images.






