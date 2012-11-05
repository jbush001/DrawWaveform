Every once in a while, I've needed to produce a sample waveform diagram for documentation.
Omnigraffle and Visio have some templates, but it's painful to line all the bits up.  There are also some fonts that contain
pieces of waveforms, which is easier but doesn't look quite as nice and also don't allow labeling of traces easily.

This is a postscript library that allows creating waveform images.  The waveforms can
be defined by calling a small set of library functions (the program to do this is
at the end of the source file).

_numclocks_ _numsignals_ __startwaveform__<br>
  Begins drawing a new waveform with the specified number of clock transitions and signals 
  Note that the clock will be drawn automatically.

_name_ __newsignal__<br>
  Starts a new signal with the specified name
  
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