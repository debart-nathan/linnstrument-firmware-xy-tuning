An unofficial LinnStrument firmware with XY-tuning
==================================================

This is an unofficial modification of LinnStrument's firmware, with a flexible way of tuning the keys. You can find about LinnStrument and its official firmware from these pages:

  https://www.rogerlinndesign.com/linnstrument <br>
  https://github.com/rogerlinndesign/linnstrument-firmware

The inspiration of this modification can be found in this post:

  https://www.kvraudio.com/forum/viewtopic.php?f=263&t=559271


### Motivation

The original LinnStument has one parameter for setting the _row offset_, which is good for most use cases. The LinnStrument's total range is mostly limited by the number of rows, because no matter how many columns you have, the keys will be mostly duplicated because each row only shifts only a few notes to the left. The default number of this shift (called row offset) is 5, which is fourth tuning.

Some people have found ways to use the LinnStrument turned 90 degrees so that they can have more rows. This can achieve a large range comparable to a grand piano. For example, Jesse Washmon's playing piano pieces with LinnStrument:

  https://www.youtube.com/watch?v=KdGFXX-kAig <br>
  https://www.youtube.com/watch?v=164qLQyt29g

But without chaning the firmware, this vertical configuration will need extra software, and will be complex and inflexible, so I decided to modify the firmware. I added a parameter called _column offset_ to global settings. This would make LinnStrument able to achieve vertical playing and a even wider range of other tunings. In addition to the previously mentioned vertical way of playing, you can also use LinnStrument like a Janko keyboard etc.


### Compiling the firmware

First, follow these instructions on LinnStrument's support page for compiling the firmware:

  https://www.rogerlinndesign.com/support/support-linnstrument-source-code

Notice two additional things for a "safe update":

  1. From Arduino IDE's Preferences, you need to check _"Show verbose output during..."_ for compiling and uploading in order to see where the compiled files are.
  2. In order to copy the compiled firmware binary into the LinnStrument Updater app, you need to right click on the app, and choose _Show Package Contents_, and then find the location of the file in _Resources_ directory.


### How to use

This modified firmware will behave almost the same as the old one if you don't do anything special except that +7 row offset button will not work in the old way. It is modifed to have the new function for setting the new _column offset_ parameter.

To use the vertical mode, _press and hold_ the +7 row offset button, and a slider screen will appear, allowing you to set the new _column offset_ parameter. The default setting of _column offset_ is 1, with which the LinnStrument behave in the usual way.

Set column offset to 5, and set row offset to -1, then you can play LinnStrument vertically with the full range of grand piano.

Let's see how this works. Let's call the row offset "R" and the column offset "C", then the original fourth tuning can be expressed as "R:+5 C:+1", which means _If you go up one row, increase 5 semitones. If you go right one column, increase 1 semitone.

Similarly, the usual fifth tuning can be expressed as "R:+7 C:+1". Because I removed the function for +7 row offset button, if you need fifth tuning, you will need to press and hold the +OCTAVE button and set the _custom row offset_ to +7.

With the new column offset parameter, you can use LinnStrument in these interesting ways.

- A vertical fourth tuning as used by Jesse Washmon for this piano playing can be expressed as "R:-1 H:+5".
- I like the vertical thirds tuning, can be expressed as "R:-1 V:4".
- Janko layout can be expressed as "R: 1 C: 2".

And more...


### About pitch slides

I haven't changed anything about pitch slides, so after turning the LinnStrument 90 degrees, pitch slides will work in its old way. This means that you need to slide up/down instead of left/right for pitch slides.

This may be inconvenient, but consider that most people will use this vertical way for piano pieces, which doesn't need pitch slide, this might be okay.


### Feedback

If you have questions, suggestions, please file an issue on GitHub, I'll try my best to improve this while I have time.

I hope you find this way fun to use!
