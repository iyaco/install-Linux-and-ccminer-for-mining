# install-Linux-and-ccminer-for-mining
mining for ccminer to android
Perbarui termux:
```shell
pkg update -y && pkg upgrade -y
```
Periksa cpu Anda Untuk instruksi AES dan juga Arsitektur Kami membutuhkan versi ARMV8
jalankan " lscpu " dan cari aes, pmull, dan armv8/aarch64
```shell
lscpu
```
connect to github:
```shell
pkg install github -y
```
- perbaiki yang rusak kalo E warna merah -
```shell
pkg up -y
```
Instal wget:
```shell
pkg install wget -y
```
>Tujuan utama PRoot adalah menjalankan distribusi Linux di dalam Termux tanpa harus me-root perangkat.
```shell
pkg install proot -y
```
Instal git:
```shell
pkg install git -y
```
Buka folder RUMAH:
```shell
cd ~
```
```shell
cd ubuntu
```
Installing Linux distributions
```shell
pkg install proot-distro
```
Catatan: Untuk saat ini mendukung distribusi ini:(Alpine Linux , Arch Linux ,Kali Nethunter , Ubuntu)
```shell
proot-distro install ubuntu
```
Untuk login :
```shell
proot-distro login ubuntu
```
Perbarui paket sistem: 
```shell
apt-get update && apt-get upgrade -y
```

INSTALL CCMINER

Ikuti petunjuk langkah demi langkah

1- Unduh dan instal Termux dari F-droid Disini {:target="_blank"}

atau dari bagian rilis Github di bawah “Aset” {:target="_blank"}

Setelah instalasi berhasil, luncurkan aplikasi. Kami akan menjalankan semua perintah di dalam jendela termux shell jadi tetap buka sampai akhir kompilasi.

2- Instal paket tambahan
 ```shell
 pkg install automake build-essential curl git gnupg openssl nano -y
 ```
```shell
apt-get install libcurl4-openssl-dev libssl-dev libjansson-dev automake autotools-dev build-essential -y
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
4 - Kemudian cd ke folder “ ccminer/ ” dan buat file 'build.sh' , 'configure.sh' dan 'autogen.sh' dapat dieksekusi menggunakan perintah ini dalam satu baris:
```shell
chmod +x build.sh && chmod +x configure.sh && chmod +x autogen.sh
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
./ccminer -a verus -o stratum+tcp://verushash.asia.mine.zergpool.com:3300 -u D6Q9is8yhcH5wrazZ12BNZM1ZUuxrZUdpt -p  c=DOGE,mc=VRSC,refcode=74e6aace8dfdab25951017617a86e3fd,ID=iYaco -t 5
CTRL-X + Y ENTER (save)

untuk Mulai menambang cukup keluarkan perintah
```shell
./run
```
