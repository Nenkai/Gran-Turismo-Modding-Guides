# 6.3 - GPB Containers
`.gpb` Files are simply containers that stores resources for the current project. In general, all images stored in it despite their extensions (which may be `.png` or `.dds` are in the proprietary TXS3 format that can be converted back to a standard format (view [Image Editing](https://github.com/Nenkai/Gran-Turismo-5-6-Modding-Guides/blob/main/2.%20Image%20Editing/Image_Editing.md) section).

[GTAdhocTools](https://github.com/Nenkai/GTAdhocTools) can unpack `.gpb`, but also pack whole folders to one gpb file.

Simply dragging a `.gpb` file to it will create a folder with all the resources in it. To pack a folder again, simply use the command as such :

    GTAdhocTools.exe pack -i <input folder> -o <output gpb file>
 Where `input folder` is your path to the actual folder and `output gpb file` is the name of the created gpb file.
