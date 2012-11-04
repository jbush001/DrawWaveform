Every once in a while, I've needed to produce a sample waveform diagram for documentation.
Omnigraffle and Visio have some templates, but I've found it a bit of a pain to work with,
especially when I want to label traces.  There are also some fonts that contain
bits of waveforms, but they also don't allow labeling of traces easily.

This is a postscript library that allows creating waveform images.  The waveforms can
be defined at the bottom of the file by calling library functions:

<numclocks> <numsignals> __startgraph__
  Begins drawing a new graph with the specified number of clocks and signals 
  Note that the clock will be drawn automatically.

<name> __newwave__
  Starts a new waveform (signal) with the specified name
  
<value> <numclocks> __drawbit__
  Draws a single bit waveform with a given value for a specified number of clocks
  
<label> <numclocks> __drawknown__
  Draws a multi-bit waveform with the given label
  
<numclocks> __drawunknown__
  Draw a multi-bit waveform that is unknown. It will be filled with gray
  
<numclocks> __drawhiz__
  Draw a portion of signal that is floating (high impedance)
  
This can be invoked from ghostscript (gs waveform.ps) or you can double click the 
postscript file directly on a Mac.