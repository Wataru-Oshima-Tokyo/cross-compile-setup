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
![GitHub Logo](/images/menu.png)
 


 
