LinnStrument firmware with XY-tuning 
====================================

This is an unofficial modification of LinnStrument's firmware, with a flexible way of tuning the keys. You can find about LinnStrument and its official firmware from these pages:

  https://www.rogerlinndesign.com/linnstrument <br>
  https://github.com/rogerlinndesign/linnstrument-firmware

The inspiration of this modification can be found in this post:

  https://www.kvraudio.com/forum/viewtopic.php?f=263&t=559271


### Motivation

The original LinnStument has one parameter for setting the _row offset_, which is good for most usages. The LinnStrument's total range is mostly limited by the number of rows, because no matter how many columns you have, they keys will be mostly duplicated.

Some people have found it useful to use the LinnStrument turned 90 degrees, so that they can have more rows and achieve a large range comparable to a grand piano. For example, Jesse Washmon's playing piano pieces with LinnStrument:

  https://www.youtube.com/watch?v=KdGFXX-kAig <br>
  https://www.youtube.com/watch?v=164qLQyt29g


To achieve this setting and even more general settings I added a parameter called _column offset_"_ to global settings. This would make LinnStrument able to achieve a even wider range of tunings. I addition to the previously mentioned way, you can also use it like a Janko keyboard.


### Compiling the firmware

First, follow these instructions for compiling the firmware:

  https://www.rogerlinndesign.com/support/support-linnstrument-source-code

Notice two additional things for a "safe update":

  1. From Arduino IDE's Preferences, you need to check "Show verbose output during..." for compiling and uploading in order to see where the compiled files is.
  2. In order to copy the compiled firmware binary into the LinnStrument Updater app, you need to right click on the app, and choose "Show Package Contents", and then find the location of the file in _Resources_ directory.


### How to use

This modified firmware will behave almost the same as the old one if you don't do anything special, except that +7 row offset button will not work in the old way because it is modifed to have the new function for setting the new _column offset_ parameter.

In this modified firmware, you can press and hold the +7 tuning button, and a slider screen will appear, allowing you to set the new _column offset_ parameter. The default setting of _column offset_ is 1, in which the LinnStrument behave in the usual way.

Let's call the column offset "C", and the row offset "R", then the original fourths tuning can be expressed as "R:+5 C:+1", which means _If you go up one row, increase 5 semitones. If you go right one column, increase 1 semitone._

Similarly, the usual fifth tuning can be expressed by "R:+7 C:+1". Because I removed the function for +7 row offset button, if you need it, you will need to press and how the +OCTAVE button and set the custom row offset to +7.

Now the interesting part. You can set the LinnStrument to work in the vertical modes with large range. 

- A vertical fourth tuning as used by Jesse Washmon for this piano playing can be expressed as "R:-1 H:+5". 
- I like the vertical thirds tuning, can be expressed as "R:-1 V:4".
- Janko layout can be expressed as "R: 1 C: 2".


### About pitch slides

I haven't changed anything about pitch slides, so after turning the LinnStrument 90 degrees, pitch slides will work in its old way. This means that you need to slide up/down instead of left/right for pitch slides.

This may be inconvenient, but consider that most people will use this vertical way for piano pieces, which doesn't need pitch slide, this might be okay.


### Feedback

If you have questions, suggestions, please file an issue on GitHub, I'll try my best to improve this while I have time.

I hope you find this way fun to use!
