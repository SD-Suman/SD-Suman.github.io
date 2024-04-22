---
layout: post
title: R and Python in fresh Linux OS install
subtitle: Installing R Studio, setting up Anaconda and your environments in a fresh Linux install.
tags:
  - r
  - python
  - linux
published: true
---

[//]: # (cover-img: /assets/img/path.jpg)
[//]: # (share-img: /assets/img/path.jpg)
[//]: # (thumbnail-img: /assets/img/thumb.png)

I recently did a fresh install of linux for the _nth_ time (remember to always backup your precious files!). History of my linux use is, as predictable, a slow Windows 7 PC. Now I cannot imagine going back to Windows anymore.


> Linux Mint Cinnamon ---> Linux Mint MATE ---> MX Linux Fluxbox ---> Ubuntu ---> MX Linux Xfce


Here I followed the natural transition from a full fleged Linux distro with huge games and office included to lighter one (MATE) and now to one of the lightest Fluxbox. Fluxbox doesn't come with any junk apps and doesn't even care about basic customization - a total no nonsense, light, fast OS. I recommend following a similar transition to get to know the operations and to ease into Linux if you are coming from Windows - you gradually even pick up a lot of basic terminal coding along the way. The downside of a new OS, however, is how much time it takes to get back all your packages so your old codes work perfectly fine.


Here I list out the first steps to get your Linux system up and running quickly as I have had to replicate most of these process in the n fresh installs I have done so far. 

### For R Studio

While installing R and R-Studio couldn't be more [simpler](https://www.rstudio.com/products/rstudio/download-server/debian-ubuntu/), Linux doesn't come pre-installed with several dependencies and system packages. So below are a bunch of dependencies you may need to install (through the terminal) which I got through non-zero exits error while installing R packages. Please note that your linux system may be different and may need different dependencies.

    sudo apt-get install libcurl4-openssl-dev
    sudo apt install libudunits2-dev
    sudo apt install libssl-dev
    sudo apt install libprotobuf-dev
    sudo apt install libjq-dev
    sudo apt install libfontconfig1-dev
    sudo apt install unixodbc-dev
    sudo apt install protobuf-compiler
    sudo apt install libprotobuf-dev
    sudo apt install libjq-dev
    sudo apt install libavfilter-dev
    sudo apt-get install cargo
    sudo apt install libv8-dev
    sudo apt install cmake
    sudo add-apt-repository ppa:marutter/c2d4u
    sudo apt-get install -y libssl-dev
    sudo apt install libgdal-dev
    sudo apt-get install gdal-bin proj-bin
    sudo apt-get install libharfbuzz-dev  libfribidi-dev

Two newly discovered missing packages in the MX Linux distro:

    sudo apt-get install gfortran
    sudo apt install r-cran-mvtnorm

### For Python

Again super simple [instructions](https://docs.anaconda.com/anaconda/install/linux/) to follow. 

After the steps above, you might need to add the path environment variable in .bashrc file using:

    nano ~/ .bashrc 

(to enter into edit mode)

and paste the following line at the end of the file: 

    export PATH="/home/username/anaconda3/bin:$PATH"

After saving and closing the file, do:

    source ~/.bashrc

Another thing that is religiously required to be done before installing Linux is to get all of your conda environments downloaded (as you might have added new modules and updated it). The [documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) pages are the best place to go as a rule, especially for R, Python and its modules, although there are ton of other resources as well. Use the code:

To list out the environments you have: 

    conda env list


To save your environment to further save it in backup:
    conda activate <environment_name>
    conda env export > environment.yml


Make sure you back up these .yml files as well.

To get it running in the new OS: 
    conda env create -n <your_prefered_env_name> --file environment.yml

You may temporarily copy the environment file to your home folder or change the path in terminal to access the file. I do the first. 


#### Creating Alias 

This is the most helpful thing since you do this everyday. I have also recently shifted to jupyer lab from jupyter notebook and it is a bliss how it defaults to the previously opened files as is - even in my fresh install! 

Creating alias is beautifully explained in this [link](https://www.tecmint.com/create-alias-in-linux/). 

To check existing alias:

    alias 

For alias for different Python IDEs, I generally have the following lines added to my .bashrc file:

    alias xj="conda activate ox && jupyter notebook"
    alias xs="conda activate ox && spyder"
    alias xd="conda deactivate"

And a new favorite:

    alias xl="conda activate ox && jupyter lab"

All done! 

In addition to the above there is usual installation of software such as QGIS, Postgres SQL and PGAdmin4, Google Earth Pro, GIMP, LibreOffice, PDF merger etc. I write this to help other beginners and for myself when I yet again do a fresh install of a better, lighter, faster Linux OS. For now, [MX Linux](https://mxlinux.org/) has been a feather light experience and best among any linux I have used without any junk (that I know of). Ubuntu comes with a ton of bloat and is super slow compared to MXLinux Fluxbox. But ubuntu looks so much nicer - still of no use if its slow. 

The best things about MX Linux is its Bash Config and Clipboard which stores previous copied lines as well and is available as a tray icon in the bottom toolbar next to time. The worst thing is it doesn't readily show the power icon on the same toolbar. I am still keeping the MX Linux for a while and not switching as the pros outweigh the cons in a great proportion.  

PS: ox is my environment which exclusively is focused on OSMNX and NetworkX which I am a huge fan of. Please visit [Geoff Boeing's OSMNX page](https://geoffboeing.com/tag/osmnx/) for more info on OSMNX.
