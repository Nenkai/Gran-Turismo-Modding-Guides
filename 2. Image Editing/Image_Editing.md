# Image Editing

PS3-era and even GTPSP uses "TXS3" as an image format, which is pretty much just DDS.

[TXS3Converter](https://github.com/Nenkai/TXS3Converter/releases/tag/1.1.3) can convert standard images (.png, .jpg, etc) into that format. Download it and extract it.

You'll also need to download and place [TeXConv](https://github.com/microsoft/DirectXTex/releases) in the same folder.

Most of them are located in the `piece` global folder.

# .img to .png

* Open `cmd` in that folder and place your `.img` file in the tool folder. 
* Run `TXS3Converter <your image file`.

If you're converting back later on you might want to take note of the image format that the tool prints into the console.

# .png/jpg/bmp to .img

* Open `cmd` in that folder and place your standard image in the tool folder. 
* Run `TXS3Converter --<DXT3/DXT5/DXT10> <your image file>`. You need to know the format before hand. Converting a .img file to normal image will show that.