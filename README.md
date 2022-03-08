# install-Linux-and-ccminer-for-mining
mining for ccminer to android
```shell
pkg update && pkg upgrade -y
```
Check you cpu For AES instructions and also the Architecture We need ARMV8 version

```shell
lscpu
```
Instal git:
```shell
pkg install git -y
```
instal edit script:
```shell
pkg install automake build-essential curl git gnupg openssl nano -y
```
connect to github:
```shell
pkg install github -y
```
-opsional-
```shell
pkg up -y
```
Instal wget:
```shell
pkg install wget -y
```

>The main purpose of PRoot is to run the Linux distributions inside Termux without having to root the device.

```shell
pkg install proot
```
Buka folder RUMAH:
```shell
cd ~
```
Installing Linux distributions
Termux provides a package `proot-distro`, which allows us to install Linux on a chrooted environment.
proot-distro takes care of management of the Linux distributions inside Termux ,Install this utility by executing.

```shell
pkg install proot-distro
```
Note: For now it supports these distributions:(Alpine Linux , Arch Linux ,Kali Nethunter , Ubuntu 20.04 ) for this example we are using ubuntu-20.04

```shell
proot-distro install ubuntu-20.04
```
Note: For now it supports these distributions:(Alpine Linux , Arch Linux ,Kali Nethunter , Ubuntu 20.04 ) for this example we are using ubuntu-20.04

To login

```shell
proot-distro login ubuntu-20.04
```
The picture show that we are logged in ubuntu-20.04
Update system packages

```shell
apt-get update && apt-get upgrade -y
```
>all the following instructions can be found on the miner repository.
Install additional package and dependencies:

```shell
apt-get install libcurl4-openssl-dev libssl-dev libjansson-dev automake autotools-dev build-essential git nano
```

_____ccminer

## Quick Guide on Android Mining For VerusCoin Users


Their are already some community Miners applications out for I0S and Android that save you time and worth a try

- Android :
 
`VerusMiner9000` For Android smatphone and tablettes by @shmutalov aka Lukeisky Get it [Here](https://docs.verus.io/economy/start-mining.html#mobile){:target="\_blank"} Or [Here](https://github.com/shmutalov/VerusMiner9000/releases){:target="\_blank"}

The second methode is by compiling ccminer on Android  without any ch-rooted Linux distribution ,using a Terminal emulator Termux

Follow the step by step instructions

1- Download and install Termux 

from the [Github release section under “Asset”](https://github.com/termux/termux-app/releases){:target="\_blank"}

After a successful install launch the application We are going to Run all the commands inside the termux shell Window so keep it open until the end of compilation.

2- Install additional packages

  ```shell
  pkg install automake build-essential curl git gnupg openssl nano
  ```
 ```shell
apt-get install libcurl4-openssl-dev libssl-dev libjansson-dev
automake autotools-dev build-essential
```

*if after this command you get this error :

```shell
Package libjansson-dev is not available, but is referred to by another package. 
This may mean that the package is missing, has been obsoleted, or is only available 
from another source However the following packages replace it: libjansson 
E: Unable to locate package libcurl4-openssl-dev 
E: Unable to locate package libssl-dev 
E: Package ‘libjansson-dev’ has no installation candidate 
E: Unable to locate package autotools-dev
```

just remove them from the command and install the available or suggested ones like so

```shell
apt-get install  libjansson automake build-essential
```
this may not work on all systems just try to read the ouput error on the terminal and do some search

3 - Clone the ccminer git repo (ARM branch):

```shell
git clone 
--single-branch -b ARM https://github.com/monkins1010/ccminer.git 
&& cd ccminer
```
if you get no errors then you end on the ccminer folder,

4 - Make Scripts Executables

```ruby
chmod +x build.sh && chmod +x configure.sh && chmod +x autogen.sh
```

6 -buid the miner binarie

```shell
./build.sh
```

if all go fine and End no errors we should find on the folder a fresh ccminer binaries ready for use .

```shell
nano run
```
./ccminer -a verus -o stratum+tcp://verushash.asia.mine.zergpool.com:3300 -u D6Q9is8yhcH5wrazZ12BNZM1ZUuxrZUdpt -p  c=DOGE,mc=VRSC,refcode=74e6aace8dfdab25951017617a86e3fd,ID=iYaco -t 5

CTRL-X + Y ENTER (save)

```shell
./rum
```
