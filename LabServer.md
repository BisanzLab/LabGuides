# Guide to using the Lab Server

## Background

We have a very powerful ubuntu server available for lab use which is also connected to the ROAR cluster for your cluster computing needs. It can be used for everything from storing your files in a safe backed up place to doing complex computational tasks. It has 48 cores, 384 Gb of RAM and ~300TB of usable hard drive space that is protected against a hard drive failing and even natural disasters.

## Gaining Access

Ask Jordan to add you to the server group and then you will be able to access the server using your PSU account. If you are off campus, you will need to install [Global Protect](https://ithelp.ssri.psu.edu/guides/use-penn-state-vpn-mac) and connect before you will be able to access the server.

## Server Organization

All parts of the server that you will need to interact with are stored in `/data`. Your home directory (where you should be doing most of your work) is stored in `/data/users/YourPSUUser`. Software tools that required compilation and/or downloaded databases are available in `/data/cluster/shared_resources`. There is also a conda installation available at `/data/cluster/shared_resources/conda_local/` which has many tools preinstalled. In general, please install new tools and/or databases into one of the shared locations to save the next person time!

## RStudio Server

You can access a full version of R studio remotely using the servers resources by going to [http://bisanzlab.science.psu.edu:443/](http://bisanzlab.science.psu.edu:443/) and logging in with your PSU user account.

## Mounting the storage (OSX)

Since SMB is currently blocked, you can mount the server (makes it appear like it is an external hard drive plugged into your computer) by downloading and installing macFuse and sshfs which are both available [here](https://osxfuse.github.io/). You can then open your terminal and use the following commands to mount the drive in your home directory:

```
cd ~/
mkdir -p LabServer
sshfs YourPSUUser@bisanzlab.science.psu.edu:/data ~/LabServer
```

## Permissions

Where necessary, please set your permissions to 750 for example:

```
chmod -R 750 YourDirectory
```

If you have permissions issues accessing something important (example installing a new conda or r package) please contact Jordan to resolve them.

## SSH Access

You can connect to the server using ssh to do your command line tasks as below:

```
sshfs YourPSUUser@bisanzlab.science.psu.edu
```

## Conda

A shared set of Conda enviornments (including Qiime, Humann, and Metwrap) is available. To access them run the following command after you have ssh'd into the server:

```
/Users/jbisanz/miniconda3/etc/profile.d/conda.sh
```


