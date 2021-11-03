# Guide to using the Lab Server

## Background

We have a very powerful ubuntu server available for lab use which is also connected to the ROAR cluster for your cluster computing needs. It can be used for everything from storing your files in a safe backed up place to doing complex computational tasks. It has 48 cores, 384 Gb of RAM and ~300TB of usable hard drive space that is protected against a hard drive failing and even natural disasters.

## Gaining Access

Ask Jordan to add you to the server [user management group](https://accounts.psu.edu/manage) and the samba users (sudo smbpasswd -a) and then you will be able to access the server using your PSU account. If you are off campus, you will need to install [Global Protect](https://ithelp.ssri.psu.edu/guides/use-penn-state-vpn-mac) and connect before you will be able to access the server.

## Note for windows users

You will need to install a bash terminal. This can be done following the instructions [here](https://itsfoss.com/install-bash-on-windows/).

## Note for mac users

You may wish to change the default terminal on your computer to bash. Open terminal and run this command:

```
chsh -s /bin/bash
```

## SSH Access

You can connect to the server using ssh to do your command line tasks as below. Do this through your terminal application. This will create a home directory for you and will be necessary before going forward.

```
ssh YourPSUUser@bisanzlab.science.psu.edu
```

## Server Organization

Your home directory (where you should be doing most of your work) is stored in `/home/YourPSUUser`. Software tools that required compilation and/or downloaded databases are available in `/data/shared_resources`. There is also a conda installation available at `/data/shared_resources/conda_local/` which has many tools preinstalled. In general, please install new tools and/or databases into one of the shared locations to save the next person time!

## RStudio Server

You can access a full version of R studio remotely using the servers resources by going to [http://bisanzlab.science.psu.edu:443/](http://bisanzlab.science.psu.edu:443/) and logging in with your PSU user account.

## Mounting the storage

You can use samba to connect to the lab server's storage which makes it appears like the server is an external hard drive on your computer. On OSX: Open Finder > command K > add the server address `smb://bisanzlab.science.psu.edu` > click connect > log in with your PSU ID > choose Bisanz_Home. The server will now appear under Locations.

If on windows, start by enabling samba following the instructions [here](https://www.asus.com/support/FAQ/1037477/). Thensee this [link](https://www.techrepublic.com/article/how-to-connect-to-linux-samba-shares-from-windows-10/) and connect to `\\bisanzlab.science.psu.edu\Bisanz_Home.`

## Permissions

Where necessary, please set your permissions to 750 for example:

```
chmod -R 750 YourDirectory
```

If you have permissions issues accessing something important (example installing a new conda or r package) please contact Jordan to resolve them.


## Conda

A shared set of Conda enviornments (including Qiime, Humann, and Metwrap) is available. To access them run the following command after you have ssh'd into the server:

```
source /data/shared_resources/conda_local/etc/profile.d/conda.sh
```


