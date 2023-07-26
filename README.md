# tomo_ptcl
For using 2D particle picking programs on 3D tomogram volumes
split_mrc_vol.pl -- Run this first. This script uses IMOD/eTomo programs to split a 3D MRC volume reconstruction into averaged slices. Requires the IMOD command line programs "header" and "clip" to function. It works in the current working directory. When run, it prompts for the tomogram filename. Enter either a filename or "ALL" for all mrc files in the current directory. It then asks how many sections to average. It makes a new directory called "split" and puts all output files there,

The files in "split" can then be input into any desired particle picking program. Some pickers require CTF to be determined. Note that CTF determination on these files, if required, will not result in any realistic output. Ideally the picker will result in one star file per output, with a filename matching except a .star extension instead of .mrc

tomo_ptcl.pl
