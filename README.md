#NOT WORKING CODE - just here because of google code
wffmpeg is a wrapper to ffmpeg command line program, written in python. Is structured as a base library, easy to extend by combining standard ffmpeg features.

requires an ffmpeg executable file. Due to this it's (almost) multi-platform.

Common behaviour needs the use of two classess:

* FFDocument, an audio/video document who is editable by apply one or more effects 

* FFmpeg, the cli wrapper. A FFmpeg instance is used to extract metadata from files and to execute an effects chain (using one or more FFDocument objects) in order to create a new document. 

A FFmpeg object can be created by specify a path for your ffmpeg executable. Thus, it can be possible to use multiple ffmpeg instances and multiple versions.

The invocation of a FFDocument's effect method returns a new modified object. This means that effects are chainable. For example:

    ff = FFDocument("/home/leonardo/movie.flv")
    ffresult = ff.resize("50%").ltrim(10).resample(120)
