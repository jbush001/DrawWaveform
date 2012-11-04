Every once in a while, I've needed to produce a sample waveform diagram for documentation.
Omnigraffle and Visio have some templates, but I've found it a bit of a pain to work with,
especially when I want to label traces.  There are also some fonts that contain
bits of waveforms, but they also don't allow labeling of traces easily.

This is a postscript library that allows creating waveform images.  The waveforms can
be defined at the bottom of the file by calling library functions:

_numclocks_ _numsignals_ __startgraph__<br>
  Begins drawing a new graph with the specified number of clocks and signals 
  Note that the clock will be drawn automatically.

_name_ __newwave__<br>
  Starts a new waveform (signal) with the specified name
  
_value_ _numclocks_ __drawbit__<br>
  Draws a single bit waveform with a given value for a specified number of clocks
  
_label_ _numclocks_ __drawknown__<br>
  Draws a multi-bit waveform with the given label
  
_numclocks_ __drawunknown__<br>
  Draw a multi-bit waveform that is unknown. It will be filled with gray
  
_numclocks_ __drawhiz__<br>
  Draw a portion of signal that is floating (high impedance)
  
This can be invoked from ghostscript (gs waveform.ps) or you can double click the 
postscript file directly on a Mac.

![sample](https://github.com/jbush001/VectorProc/wiki/l2req-waveform.png)