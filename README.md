# linSample
A method for managing samples on the Volca Sample with Linux

## Overview
Since all the of the gui based applications for Volca Sample management were causing me headaches and getting in the way of me actually writing any tunes I decided to pull from another project and write some scripting around it so I could do all of my sample conversion, renaming, and uploading with one command.

## Dependencies
1. sox
2. aplay (from alsa-utils)
3. Wine
4. EasyVolcaSample.exe from the project by josephernest that this one is built on, found at https://github.com/josephernest/EasyVolcaSample

## Installation Instructions
1. Obtain both my project and EasyVolcaSample
2. Copy EasyVolcaSample.exe from the EasyVolcaSample project directory into the directory of linSample
3. chmod +x the install script from my project, then execute it with sudo

## Usage
1. Drop your desired samples into one directory
2. With your Volca Sample's audio in already connected to the audio out of your PC or interface, run linSample from within that directory
3. When prompted, enter the number that you want your samples to begin at. If you're overwriting the Volca's entire sample memory, 0 is a good choice. If you wanted to keep samples 0-12 and begin overwriting at 13, you would enter 13.
4. Happy jamming

## Notes
The install script isn't really needed, you can copy linSample, runevs, and EasyVolcaSample.exe into the /bin directory yourself, or wherever else you want assuming you modify all of the scripting to match. It is, however, preferable to place these files within your path, or else the one command ease of use becomes moot.

runevs isn't really a necessity if you do some mild script altering, since all it contains is one line executing EasyVolcaSample.exe with Wine. I have run into problems executing programs with Wine from within scripts in the past, but the problems are always negated by a one line script such as runevs so I chose to wrap it this way.

If you don't want to upload your sample packs straight away, or you're just packaging them for later use, you can comment out the last line of the linSample script. In your sample directory, you'll find a directory called converted, within that directory you'll find a file called out.wav. This is the file your Volca can understand and you can play it with any audio player of your choice to upload samples. You may also rename it to something memorable and store it away elsewhere to build up banks of samples you can switch between on the fly.

## Limitations
Even if you own a Sample 2, you will still only have access to the first 100 samples, being 0-99. This isn't a problem in my case because I tend to overwrite the Sample's entire memory per project

Uploading a ton of samples can take time; i've seen resulting data files upwards of 20-30 minutes, keep in mind these have to play in real time. Use the time to prepare the rest of your instruments, grab a cup of coffee, or simply for quiet reflection.
