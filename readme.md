# espeakedit

`espeakedit` is a GUI frontend which allows one to prepare and compile phoneme data for the [eSpeak][esp] speech synthesizer.

Do be careful to make sure that the versions of dictionary data produced by `espeakedit` and consumed by `espeak` are compatible.

Note: This was cloned off [Dashboard-X][dbx] who had a version of espeakedit tagged 1.46.02. The source code was taken off the initial sourceforge release of the espeakedit program. 

## Dependencies

`espeakedit` has a GUI built using the wxWidgets library (wxGTK version 2.6) (www.wxwidgets.org).

It needs the following packages (these are the names from the Ubuntu "Dapper" repository):

To run:
 * `libwxgtk2.6-0`
 * `libportaudio0`
 * `sox`

To compile, it also needs:
 * `libwxgtk2.6-dev`
 * `libportaudio-dev`

The binary has been compiled to use V18 of the PortAudio library.  If you have V19 you will need to recompile espeakedit, after copying `portaudio19.h` to replace the original `portaudio.h` file in the src directory.

## Compiling

I have now included a Makefile in the `src` directory, so it should compile, if
the wxWidgets include files (from the libwxgtk2.6-dev package) are present, by using:

  make

## Documentation

Not much yet. `docs/editor.html` is a quick run through of the main functions. `docs/editor-if.html` gives some details of the user interface.

If you want to use it to add or improve phoneme data, and you have questions, please email me.

## Data

Directory "phsource" contains the master phonemes file: "phonemes", the additional phoneme files for various languages, and all the sound files needed to compile the phoneme data into `espeak-data/phondata`, `phontab`, `phonindex`.

## praat

I use [`praat`][prt] to view and analyse speech output, either sound recordings, or output from the eSpeak synthesizer.

I (Dashboard-X) made a modification to `praat` to add a function to analyse a sample of speech and produce a file containing sequence of time-slice spectra which you can load into espeakedit to display and use as a basic for matching or creating vowel and other voiced sounds.  Details of the modification are in the directory `praat-mod`.

Unfortunately I am currently unable to compile and run `praat` on my computer, even an unmodified copy.  It compiles OK, but won't run (gets stuck with 100% CPU usage without displaying any GUI).  I don't know why this is. I have an old binary (built before I last upgraded by Linux) and that runs OK.

[prt]: http://www.praat.org/
[dbx]: https://github.com/Dashboard-X/espeakedit-1.46.02
[esp]: http://espeak.sourceforge.net/
