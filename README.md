# Elk community plugins pack

This is a meta-repository containing as submodules the projects for various plugins built for [Elk Audio OS on Raspberry Pi](https://github.com/elk-audio/).

Whenever a modification of the original project was needed for the build, the submodules point to local forks hosted on [this Github organization](https://github.com/elk-community).

Under the release section, you will find an archive with all the plugins with a directory hierarchy (`elk-plugins-pack.tar.xz`). Extract it under e.g. `/udata/plugins/` to have the VST/VST3 the plugins available on the board. 

The LV2 plugins in the pack will not be found from that path - you need to place them in a folder contained in the LV_PATH environment variable on your system/device. This should be /usr/lib/lv2/ or /usr/local/lib/lv2/, but do print it ('echo $LV2_PATH') to make sure.
The reason is the LV2 standard does not allow referencing plugins by path, only by their URI, e.g. "http://drobilla.net/plugins/mda/JX10" refers to the drobilla port of the MDA JX10 synth plugin. It is this URI you need to specify in your Sushi config files, no the path to the plugin binary [more on this in the main elk audio OS documentation page](https://elk-audio.github.io/elk-docs/html/index.html).
By typing 'lv2ls' on the terminal, you can check if the URI for the plugin you are looking for appears in the list - if not, Sushi will not be able to load it.

## Plugin status

Not all of the plugins have been thouroughly tested; the focus was getting them to build and run without Xenomai Real-Time issues.

Please report any that is not working by submitting an Issue here or, the other way around, we are looking into preparing a selection of plugins that are both high quality and work nicely with Elk - for recommendations about good candidates, feel free to post in the relative section on our forum:
https://forum.elk.audio/c/community/plugins-working-with-elk

---
Copyright 2020 Modern Ancient Instruments Networked AB, dba Elk, Stockholm, Sweden.

Original plugins released with the same original license as the original; see the corresponding projects for details.
