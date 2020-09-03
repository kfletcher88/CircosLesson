# An introduction to using Circos.

## Installation

I reccomend that you first install conda, then Circos:

### Conda
```
wget https://repo.anaconda.com/archive/Anaconda3-2020.07-Linux-x86_64.sh
bash Anaconda3-2020.07-Linux-x86_64.sh 
```
Make sure you install it in a directory with plenty of space. Such as rwmwork. This will be requested in the `bash Anaconda3-2020.07-Linux-x86_64.sh` step.\
You may need to source your bash profile to launch conda. Or `source ~./bashrc` could be added to your `~/.bash_profile` and restart your shell.

```
source ~/.bashrc 
```

### Circos

Before starting check conda is running. To confirm this, your command prompt should start `(base)`.
We will now creat a new environment for Circos, activate it and then use conda to install circos.

```
conda create --name Circos
conda activate Circos
conda install -c bioconda circos
```


You can run circos and make sure it works:
```
$ circos -h
Usage:
      # without -conf Circos will search for configuration
      circos

      # use specific configuration file
      circos -conf circos.conf

      # diagnose required modules
      circos -modules

      # detailed debugging for code components
      # see http://www.circos.ca/documentation/tutorials/configuration/debugging
      circos -debug_group GROUP1,[GROUP2,...]

      # full debugging
      circos -debug_group _all

      # absolutely no reporting
      circos ... [-silent]

      # configuration dump of a block (or block tree) of
      # any parameters that match REGEXP (optional)
      circos -cdump [BLOCK1/[BLOCK2/...]]{:REGEXP}
      circos -cdump ideogram
      circos -cdump ideogram:label
      circos -cdump ideogram/spacing

      # override configuration parameters
      circos -param image/radius=2000p -param ideogram/show=no

      # for fun - randomize all colors in the image except for
      # COLOR1, COLOR2,...
      circos -randomcolor COLOR1,[COLOR2,...]
      circos -randomcolor white,black

      # brief help
      circos -h

      # man page
      circos -man

      # version
      circos -v
```

