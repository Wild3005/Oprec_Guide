# Modul_Oprec_OpenCV

## install opencv
> sebelumnya coba kamu jalankan pada terminal ubuntumu ini ``` pkg-config --modversion opencv4```

> jika keluar versi atau angka ``` 4.2.0```, jika ada dapapa hehe cuman ngecek aja artinya kamu udah install opencv bisa langsung dipake intinya :D

> sekarang aku ngebahas untuk nge-update versi itu ke versi opencv terbaru

### Ubah versi Opencv ke versi terbaru

nah sekarang kamu copy perbaris pada terminalmu (jika barisnya diawali dengan "#" itu hanya penjelasan baris jadi yang di copy yang tidak bertanda "#")

```sh 
# Install minimal prerequisites (Ubuntu 18.04 as reference)
sudo apt update && sudo apt install -y cmake g++ wget unzip

# Download and unpack sources
wget -O opencv.zip https://github.com/opencv/opencv/archive/4.x.zip
unzip opencv.zip

# Create build directory
mkdir -p build && cd build

# Configure
cmake  ../opencv-4.x

# Build
cmake --build .
```
nah disini kalian harus sabar.....

> setelah selesai kalian masih berada pada direktori ``` ~/build``` nya lalu gunakan commad dibawah ini unruk menset ke versi terbaru opencv:

```sh
sudo make install
sudo ldconfig
```

### buat workspace opencv
> pastikan anda telah menginstall opencv dengan benar seperti perintah diatas

> __lalu ikuti arahan dibawah ini:__

> buatlah folder baru

> jika sudah buat folder workspace dengan isi didalamnya bernama folder **build**

> (opsional) tambahkan folder src pada workspace untuk menaruh file program

> buat file pada workspace bertuliskan **CMakeLists.txt**

> pada file **CMakeLists.txt** konfigurasikan atau taruh kode seperti dibawah ini:

==============================
cmake_minimum_required(VERSION 3.0)

project( oprec )

find_package( OpenCV REQUIRED )

add_executable( oprec (kode program mu) )

##add_executable( oke1 src/progrobot.cpp )

target_link_libraries( oprec ${OpenCV_LIBS} )

==============================

> jika sudah pada terminal masuk ke direktori folder build

> lalu tuliskan ``` cmake..```

> bila ingin compile code anda harus berada pada direktori build pada terminal lalu gunakan perintah ``` make```

> saat ingin menjalankan anda gunakan perintah ``` ./(nama project yang ada di file txt)```

> pada file txt atau **CMakeLists.txt** tertulis oprec jadi menjadi ``` ./oprec```


### cek versi opencv sekarang
gunakan kode dibawah ini pada filemu dan jangan lupa pada **CMakeLists.txt** pada **add_executable( (nama_projectmu) (lokasi filemu) )** ganti dengan lokasi filemu
```c++
#include <opencv2/core.hpp>
#include <iostream>

int main() {
    std::cout << "OpenCV version: " << CV_VERSION << std::endl;
    return 0;
}
```

> jika keluar ``` OpenCV version: 4.10.0-dev``` selamat anda telah mengubah opencv ke versi terbaru

## selesai :D
