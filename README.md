# netkit-dhcp-nat

##### Using Netkit for setting up and performing networking experiments.

------------

- Netkit version 2.8
- Fedora version 28

--- STEP 1: DOWNLOAD AND UNPACK ---

Download all the files of the official site to a directory of your choice. Then 
unpack them by using the following commands:

`tar -xjSf netkit-x.y.tar.bz2`
`tar -xjSf netkit-filesystem-Fx.y.tar.bz2`
`tar -xjSf netkit-kernel-Kx.y.tar.bz2`

--- STEP 1.1: SPECIFIC DOWNLOADS FOR **FEDORA USERS** ---

after unpack the files run into your terminal the following commands:

`sudo dnf install audit.x86_64 glibc.i686 glibc.x86_64`
`sudo dnf install xterm`
  
Note that all the three packages must be uncompressed while staying in the same
directory.

--- STEP 2: CONFIGURATION ---    

The first step is to set the environment variable NETKIT_HOME to the name of the
directory Netkit has been installed into. In order to access the Netkit man pages,
the MANPATH variable must be set to ":$NETKIT_HOME/man". For example, assuming 
that you have installed Netkit to /home/foo/netkit and that your shell is bash,
you would use the following commands:

  `export NETKIT_HOME=/home/foo/netkit`
  `export MANPATH=:$NETKIT_HOME/man`
  
It may also be useful to put these lines inside your shell initialization file
(.bashrc in case you are using the bash shell). 

After doing this, you need to update your PATH environment variable to include
the path to the standard Netkit commands. This is required in order to make
Netkit work properly. The entry you need to add to the PATH is
"$NETKIT_HOME/bin". For example, assuming Netkit is (still) installed into
/home/foo/netkit and that your shell is (still) bash, you would type:

  `export PATH=$NETKIT_HOME/bin:$PATH`

Again, it may be convenient to put this line inside your shell initialization
file.

--- STEP 3: CHECK YOUR CONFIGURATION ---

At this point, change the current directory to the Netkit directory:

  `cd netkit`

Now, run the check_configuration.sh script by typing:

  `./check_configuration.sh`

This script takes care of checking whether your system is configured properly to
make Netkit run. Any misconfigurations are signalled and instructions for fixing
them are reported as well. If the script exits with success, then Netkit is
ready for use.

Basically all these steps are from the official site, except about the __STEP 1.1__,
that is specific for **fedora users**.


