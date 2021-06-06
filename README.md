# cross-compile-setup
# 1.Setup the configure

## Download the compressed files from 
    http://crosstool-ng.github.io/
    
## Expand it 
    tar -jxvf crosstool-ng-{version}
    
## got to the download directry and type theses commands
    ./bootstrap
    ./configure --prefix=/opt/cross
## once it is finished, do the commands (You may need to install some additional packages)
    sudo make
    sudo make install
## Add the below line into your bash file (~/.bashrc)
    PATH=$PATH:/opt/cross/bin

# 2. make a working directry and build

## make a directry
    mkdir ~/crosstool-ng;cd crosstool-ng
## bring the template to the working directry
    ct-ng arm-unknown-eabi
## change the configure
    ct-ng menuconfig
    
## change like below
    Click the Paths and misc options
![menu config](/images/menu.png)
 
    1. Change to (${Home}/crosstool-ng/src) at Local tarballls directory
    2. Change to ({CT_TOP_DIR}/.build) at Working directory
![Path and misc options](/images/path.png)

    Click the target options
![menu config](/images/menu.png)

    1. disable the Use the MMU
    2. change () to (cortex-a7) Emit assembly for CPU
    3. change () to (neon-vfpv4) Use specific FPU
![menu config](/images/target.png)
    

## add the permission to the /opt/cross
    sudo chmod a+rwx /opt/cross

## build it 
    ct-ng build
