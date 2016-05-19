# sdsync
sdsync shall synchronise (read: copy) files from the SD card of a HD
camcorder or a H4n into a target directory.

## filetypes

### .MTS
Usually found in `$mount/PRIVATE/AVCHD/BDMV/STREAM`, contains video&audio
data, usually h264+ac3 or something like that.

### .wav
Usually found in `$mount/STEREO/FOLDER01`, contains audio data as RIFF
WAVE.

## how
* find out, if sdcards are connected to the system
 * some parameter might be in /dev/
* find out, which type of data the card contains
 * /PRIVATE/AVCHD/BDMV/STREAM is .MTS
 * /STEREO/FOLDER01 is .wav
 * also .mp4 screenrecordings in /
* copy the files to the target directory
 * some parameter might be a directory not in /dev/
* optional: delete source files
* optional: build some sort of pseudocode-to-python-code-generator…

## setup
something something fstab, might build something that will work as
root&non-root

	LABEL=rohdaten  /media/rohdaten auto    noauto,user,defaults    0       0
	/dev/mmcblk0p1  /media/mmcblk   auto    noauto,user,defaults    0       0
