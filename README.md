# install-Linux-and-ccminer-for-mining
mining for ccminer to android
Perbarui termux:
```shell
apt-get update && apt-get upgrade -y
```
Periksa cpu Anda Untuk instruksi AES dan juga Arsitektur Kami membutuhkan versi ARMV8
jalankan " lscpu " dan cari aes, pmull, dan armv8/aarch64
```shell
lscpu
```
connect to github:
```shell
apt-get install github -y
```
- perbaiki yang rusak kalo E warna merah -
```shell
apt-get up -y
```
instal wget
```shell
apt-get install wget -y
```
instal git
```shell
apt-get install git -y
```
instal make
```shell
apt-get install make -y
```
instal cmake
```shell
apt-get install cmake -y
```
instal php
```shell
apt-get install php -y
```
instal nano
```shell
apt-get install nano -y
```
instal clone
```shell
apt-get install clone -y
```
instal prot
```shell
apt-get install proot -y
```
>Tujuan utama PRoot adalah menjalankan distribusi Linux di dalam Termux tanpa harus me-root perangkat.
Go to HOME folder:
```shell
cd ~
```
Download script:
```shell
git clone https://github.com/MFDGaming/ubuntu-in-termux.git
```
or
```shell
git clone -b ubuntu18.10 https://github.com/MFDGaming/ubuntu-in-termux.git
```
Go to script folder:
```shell
cd ubuntu-in-termux
```
Give execution permission::
```shell
chmod +x ubuntu.sh
```
Run the script:
```shell
./ubuntu.sh -y
```
Now just start ubuntu:
```shell
./startubuntu.sh
```
Perbarui paket sistem: 
```shell
apt-get update -y && apt-get upgrade -y
```

INSTALL CCMINER

Ikuti petunjuk langkah demi langkah

1- Unduh dan instal Termux dari F-droid Disini {:target="_blank"}

atau dari bagian rilis Github di bawah “Aset” {:target="_blank"}

Setelah instalasi berhasil, luncurkan aplikasi. Kami akan menjalankan semua perintah di dalam jendela termux shell jadi tetap buka sampai akhir kompilasi.

2- Instal paket tambahan
 ```shell
 apt-get install libcurl4-openssl-dev libssl-dev libjansson-dev automake autotools-dev build-essential git nano
```
jika setelah perintah ini Anda mendapatkan kesalahan ini:
```shell
Package libjansson-dev is not available, but is referred to by another package. 
This may mean that the package is missing, has been obsoleted, or is only available 
from another source However the following packages replace it: libjansson 
E: Unable to locate package libcurl4-openssl-dev 
E: Unable to locate package libssl-dev 
E: Package ‘libjansson-dev’ has no installation candidate 
E: Unable to locate package autotools-dev
```
hapus saja dari perintah dan instal yang tersedia atau yang disarankan seperti itu
```shell
apt-get install  libjansson automake build-essential
```
ini mungkin tidak berfungsi di semua sistem, coba baca kesalahan keluaran di terminal dan lakukan pencarian

3 - Mengkloning ccminer git repo (cabang ARM):
```shell
git clone --single-branch -b ARM https://github.com/monkins1010/ccminer.git
```
buKa folder ccminer
```shell
cd ccminer
```
4 - Make Scripts Executables

```shell
chmod +x build.sh
```
```shell
chmod +x configure.sh
```
```shell
chmod +x autogen.sh
```
5- kemudian dapat menjalankan skrip
```shell
./build.sh
```
edit file “ run ” yang terletak di Folder ccminer
```shell
nano run
```
Ubah Pool_url , Alamat penambangan dan Nomor utas CPU , untuk menyimpan CTRL+x , tanggapi dengan Y dan tekan Enter
./ccminer -a verus -o stratum+tcp://Pool_URL:PORT -u MINING_Address.WORKER_NAME -p x -t THREADS NUMBERS

contoh:
```shell
./ccminer -a verus -o stratum+tcp://verushash.asia.mine.zergpool.com:3300 -u D6Q9is8yhcH5wrazZ12BNZM1ZUuxrZUdpt -p  c=DOGE,mc=VRSC,refcode=74e6aace8dfdab25951017617a86e3fd,ID=iYaco -t 5
```
CTRL-X + Y ENTER (save)

untuk Mulai menambang cukup keluarkan perintah
```shell
./run
```
