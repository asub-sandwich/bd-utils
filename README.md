# bd-utils
A series of scripts to aid in the process of calculating bulk density from turntable photogrammetry. Currently written in bash, but I may make a python option for Win friends. This is just a wrapper around available programs.

I also have not added anything to ensure you have the correct packages to download. Ill get to it eventually.

## exframe

**CURRENTLY ONLY FOR APPLE .MOV FILES**
takes a *.mov file and converts it to jpgs with a customizable frame rate. Used so turntable photogrammetry can be performed by taking a video instead of several pictures. Personal tests have resulted in no change in volume when done this way.

```
$ exframe path/to/input.mov path/to/output_dir 3
```
takes input.mov and converts it to jpgs, written to output_dir with 3 images generated per second of video

## fbx2obj

convert an AutoDesk ReCap mesh object (fbx) into a standard object (obj) file. This is done because AutoDesk Fusion 360 does not allow opening meshes created in their own f-ing software.

```
$ fbx2obj [-a] -i <path/to/input.fbx> -o <path/to/output.obj>

  -a: search for all fbx files in current working directory 
```

## heic2jpg

converts heic to jpg (if u are lame and want to sit there and take 35 pictures!). Converts entire directory of jpgs at a time.

```
$ heic2jpg <path/to/input_dir> <path/to/output_dir>
```

## Future

+ Python?
+ Android video/photo compat?
+ Add dependency checks (bash)
+ Commands are currently different for one program used in fbx2obj depending if you are on a rolling release or stable release disto, so i should probably account for that.
+ Might be nice to make it into one script and then choose a subcommand?

## Use & Acknowledgement
Use at your own risk, but I am more than happy to help with an issue with the scripts or with photogrammetry & bulk density.
