# tomo_ptcl
For using 2D particle picking programs on 3D tomogram volumes
split_mrc_vol.pl -- Run this first. This script uses IMOD/eTomo programs to split a 3D MRC volume reconstruction into averaged slices. Requires the IMOD command line programs "header" and "clip" to function. It works in the current working directory. When run, it prompts for the tomogram filename. Enter either a filename or "ALL" for all mrc files in the current directory. It then asks how many sections to average. It makes a new directory called "split" and puts all output files there,

The files in "split" can then be input into any desired particle picking program. Some pickers require CTF to be determined. Note that CTF determination on these files, if required, will not result in any realistic output. Ideally the picker will make an overall star file which lists all found particles from all micrographs. Warp does this, for example. For picks within cryosparc, the data can be converted to a star file using pyem. Be careful about y-axis flipping. For cryolo, the make_picks.pl script can combine the many star files into a single file.

tomo_ptcl.pl -- run this on the star file produced by particle picking. Ideally, the picker will have placed all of the particles from all of the files. It asks for thr particle size, and uses this to determine if picks on adjacent sections are for the same particle. It outputs a single 3D coordinate star file for the particle picks. This can be used directly for subtomogram generation in Warp.

satr2box.pl -- converts the 3D coordinate star file to an EMAN2 style box file. This can be usued within EMAN2 to visualize picks on a tomogram.
