# How to use docker

Using singularity from the command line. Now enabled. First raise a ticket with [hgi@sanger.ac.uk](mailto:hgi@sanger.ac.uk) and ask for the docker image you want to be installed in the TRE. You then call the .sif image for your analysis. If your pipeline has other dependencies (i.e. needs R libraries, or reference datasets etc.) you need to do the set-up outside the TRE, zip and import through the airlock (you can't do the import step yourself). Once in the TRE and after the docker image is installed, you can run the docker from the command line with  
```
singularity shell /pathway/dockerimage.sif
```

!!! tip 
    Do not forget you need to mount the directories you need for reading/writing within the singularity (i.e. \-B).
