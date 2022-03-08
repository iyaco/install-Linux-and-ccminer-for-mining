# install-Linux-and-ccminer-for-mining
mining for ccminer to android
pkg update && pkg upgrade -y

lscpu

pkg install git -y

pkg install github -y

pkg up -y

pkg install wget -y

cd ~

cd ubuntu

pkg install proot

pkg install proot-distro

proot-distro install ubuntu-20.04

proot-distro login ubuntu-20.04

apt-get update && apt-get upgrade -y

apt-get install libcurl4-openssl-dev libssl-dev libjansson-dev automake autotools-dev build-essential git nano

_____ccminer

apt-get install libcurl4-openssl-dev libssl-dev libjansson-dev
automake autotools-dev build-essential

#just remove them from the command and install the available or suggested ones like so#
apt-get install  libjansson automake build-essential

git clone - -single-branch -b ARM https://github.com/monkins1010/ccminer.git

chmod +x build.sh && chmod +x configure.sh && chmod +x autogen.sh

./build.sh

cd ccminer

nano run
CTRL-X + Y ENTER (save)

./rum
