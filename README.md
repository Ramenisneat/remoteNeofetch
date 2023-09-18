# remoteNeofetch
I wanna run neofetch with images on my school's lab servers :)

# Reason
On my school's lab servers, we do not have sudo previleges(obviously), but I need a way to show of my "sick" neofetch with my animu waifu to assert my nerd dominance to my friends.

# What I changed.
neofetch itself is just a bash script, so if you just need a normal neofetch splash with your distro's ascii art, just neofetch is enough.

If you want to handle image support, it gets weird, because neofetch runs dependencies that you install.

Without sudo means no installing which means no images :(

So I built from source the dependencies I needed (ImageMagick, icat and Iterm2-imgcat). <br>
Imagemagick is just the official Imagemagick gcc AppImage, I renamed it to convert for it to be used in neofeth. <br>
icat is built from the official repo link below. <br>
imgcat is a bash script found on the official iterm2 website.

All I did was patch in these built files into the neofetch bash script and called it a day.
**Formatting in the neofetch file is all out of wack, all I did was patch in these bins/scripts**

# Usage
- ssh into you remote using the `-X` flag i.e. ssh -X host@remote
- clone this repo
- add the directory path to your path (or just run in the directory)
- `neofetch --icat path/to/image` for pixelated ANSI images
- If on supported terminal such as kitty or iterm2, you can use `neofetch --imgcat path/to/image` for true images.

All credits for the image backends go to Imagemagick, icat and Iterm2's imgcat
- https://github.com/ImageMagick/ImageMagick
- https://github.com/atextor/icat
- https://iterm2.com/documentation-images.html
