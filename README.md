# UCSC trackHub generator

python script to creates a UCSC trackhub configuration from local directory structure

It parses a local directory structure and maps this to a UCSC trackDb.txt config

Author: Steffen Heyne, MPI-IE Freiburg, Germany

## usage example

    cd example/
    trackHub_generator.py -o mm10_upload mm10/

Parses mm10/ directory and writes tracksDb.txt to mm10_upload/ 
It also links (symbolic) all used files to mm10_upload/ for easy cloud upload afterwards.

Recognized subdirs (in the example under mm10/)
     
    Allowed directory names: *.multiwig
                       *.composite
                       *.super
    
    Only one nesting level is supported by UCSC! So only super containers can hold one 
    level of multiwig or composite containers, not more! 

    composite/ multiwig containers can only contain tracks.
    
    The toplevel can contain tracks (not related to any container)
    
    Current code only supports *.bw|*.bigwig or *.bb|*.bigbed tracks!
