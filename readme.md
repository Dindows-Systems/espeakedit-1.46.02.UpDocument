# espeakedit

espeakedit is a GUI frontend which allows one to prepare and compile phoneme
data for the [eSpeak][esp] speech synthesizer.

Do be careful that the versions of dictionary data produced by espeakedit and
consumed by espeak are compatible.

Note: This was cloned off [Dashboard-X][dbx] who had a version of espeakedit
tagged 1.46.02. The source code was taken off the initial sourceforge release
of the espeakedit program. 

## Dependencies 

`espeakedit` has a GUI built using [version 2.6][wxw] of the wxWidgets library
for GTK.

On Ubuntu 12.04.2 LTS "Precise Pangolin", it requires the following packages
to compile:

   * libwxgtk2.6-dev
   * libportaudio-dev
   * libwxgtk2.6-0
   * libportaudio0
   * sox

The last three are enough to run a precompiled `espeakedit` binary.

Note: The binary has been compiled to use V18 of the PortAudio library. If 
you have V19 you will need to recompile espeakedit. First copy `portaudio19.h`
to replace the original `portaudio.h` file in the `src` directory.

## Compiling

I have now included a Makefile in the src directory, so it should compile, if
the wxWidgets include files are present, by using:

    make

## Documentation

Not much yet.  `docs/editor.html` is a quick run through of the main functions. 
`docs/editor-if.html` gives some details of the user interface.

## Data

Directory `phsource` contains the master phonemes file `phonemes`, additional
phoneme files for various languages, and all the sound files needed to compile
the phoneme data into `espeak-data/phondata`, `phontab`, `phonindex`.

## Praat (comments presumed to be from [Dashboard-X][dbx])

I use [`praat`][pra] to view and analyse speech output, either sound recordings,
or output from the eSpeak synthesizer.

I made a modification to Praat to add a function to analyse a sample of speech
and produce a file containing sequence of time-slice spectra which you can load
into `espeakedit` to display and use as a basis for matching or creating vowel
and other voiced sounds.  Details of the modification are in the directory `praat-mod`.

Unfortunately I am currently unable to run praat on my computer, even an unmodified
copy.  It compiles OK, but won't run (gets stuck with 100% CPU usage without 
displaying any GUI).  I don't know why this is.

I have an old binary (build before I last upgraded by Linux) and that runs OK.

[dbx]: https://github.com/Dashboard-X/espeakedit-1.46.02
[esp]: http://espeak.sourceforge.net/
[wxw]: http://www.wxwidgets.org/
[pra]: http://www.praat.org/
