---
title: Windows Subsystem for Linux
description: Dengan WSL, Anda tidak perlu lagi menggunakan mesin virtual atau melakukan dual boot untuk menikmati berbagai manfaat dari sistem operasi Linux.
author: admin
date: 2022-07-01 20:55:00 +0700
categories: [Notes]
tags: [wsl]
image:
  path: "activity-debug/image/upload/t_4_kanan_bawah/v1730097987/crugvjzks468cogokixb.jpg"
  width: 1000   # in pixels
  height: 400   # in pixels
  alt: infografis-wsl
---

> Artikel di laman ini akan terus saya update seiring ada perubahan pada catatan yang saya buat
{: .prompt-info }

### Apa Itu WSL (Windows Subsystem for Linux)?

  WSL atau Windows Subsystem for Linux adalah fitur yang sangat berguna di Windows yang memungkinkan Anda menjalankan lingkungan Linux secara langsung di dalam sistem operasi Windows Anda. Dengan WSL, Anda tidak perlu lagi menggunakan mesin virtual atau melakukan dual boot untuk menikmati berbagai manfaat dari sistem operasi Linux.

### Mengapa WSL Berguna?

  - **Akses ke Perangkat Lunak Linux:** 
  
    Anda bisa menjalankan berbagai aplikasi dan alat baris perintah Linux yang tidak tersedia secara native di Windows, seperti berbagai distribusi Linux (Ubuntu, Debian, Fedora, dll.), alat pengembangan, dan software khusus lainnya.

  - **Integrasi dengan Windows:** 
    
    WSL terintegrasi dengan baik dengan Windows, sehingga Anda dapat dengan mudah beralih antara lingkungan Windows dan Linux. File dan folder dapat diakses dari kedua sistem operasi.

  - **Pengembangan Aplikasi:** 
    
    WSL sangat berguna bagi pengembang yang ingin menguji dan membangun aplikasi lintas platform. Anda bisa menggunakan alat pengembangan yang sama yang digunakan di lingkungan Linux.

  - **Otomatisasi Tugas:** 
    
    Anda bisa menggunakan skrip dan alat otomatisasi Linux untuk melakukan berbagai tugas, seperti pengelolaan file, backup, dan deployment.

  WSL adalah alat yang sangat berharga bagi pengguna Windows yang ingin memanfaatkan kekuatan dan fleksibilitas sistem operasi Linux. Jika Anda seorang pengembang, administrator sistem, atau pengguna yang ingin mencoba Linux, WSL adalah pilihan yang sangat baik.

### Bagaimana Cara Kerja WSL?

  WSL menyediakan lapisan kompatibilitas yang memungkinkan kernel Linux berjalan di atas kernel Windows. Ini berarti Anda dapat menjalankan aplikasi Linux secara langsung di Windows, seolah-olah Anda sedang menggunakan komputer Linux.

### WSL 1 vs WSL 2

Ada dua versi utama WSL:

- **WSL 1:** Versi awal WSL yang lebih ringan dan mudah digunakan.

- **WSL 2:** Versi yang lebih baru dengan performa yang lebih baik, terutama untuk operasi I/O dan kompatibilitas sistem file. WSL 2 menggunakan mesin virtual ringan untuk menjalankan kernel Linux.

### Keuntungan Menggunakan WSL:

- **Fleksibilitas:** Anda bisa memilih distribusi Linux yang sesuai dengan kebutuhan Anda.

- **Efisiensi:** WSL lebih efisien dibandingkan dengan mesin virtual.

- **Kemudahan Penggunaan:** Integrasi yang baik dengan Windows membuat WSL mudah digunakan.

### Contoh Penggunaan WSL:

- **Pengembangan web:** Menggunakan editor kode seperti Visual Studio Code dengan ekstensi untuk pengembangan web di lingkungan Linux.

- **Machine learning:** Melatih model machine learning menggunakan TensorFlow atau PyTorch di dalam lingkungan Linux.

- **Administrasi sistem:** Mengelola server Linux jarak jauh atau menjalankan skrip untuk otomatisasi tugas.


### Install & Config

- <https://docs.microsoft.com/en-us/windows/wsl/install>
- <https://ubuntu.com/tutorials/install-ubuntu-on-wsl2-on-windows-11-with-gui-support#1-overview>

### Menjalankan Ubuntu di WSL

#### Menggunakan Start Menu

1. Menggunakan start menu,
2. cari `Ubuntu`
3. klik `Ubuntu`

#### Menggunakan Powsershell

1. Open Powershell, (*press <kbd>WinCtl + x</kbd>, type <kbd> i </kbd>*)
2. type `wsl` on terminal
3. dan kamu will login to ubuntu in current location you type the command

> Or you can select from terminal dropdown tab, to open new tab as ubuntu wsl, seperti pada gambar berikut
>   {: .prompt-info }

![Desktop View](https://i.imgur.com/YzzYQZN.png){: .shadow w="40%" }

### Reinstall Ubuntu di WSL
> clean distro / wipe up data
1. cek distro: `wls -l`
2. unregister: `wsl --unregister <DistroName>`
3. install



### Usefull Command

#### Powershell

| Command                     | Descriptions                 |
| --------------------------- | ---------------------------- |
| wsl -v                      | cek versi                    |
| wsl -l                      | cek distro                   |
| wsl -l -v                   | cek versi dan list distro    |
| wsl --help                  | man page wsl                 |
| wsl --list --online         | list distro online           |
| wsl.exe --install           | install default distribution |
| wsl --set-default-version 2 | set to version 2 wsl version |

> Install other distro: `wsl --install -d <Distribution Name>`
> {: .prompt-tip }

#### Ganti Default User

| Command                                    | Descriptions                     |
| ------------------------------------------ | -------------------------------- |
| ubuntu config --default-user new_user_name | ganti default user distro ubuntu |

> **NOTE:** Perintah diatas digunakan di powershell sebelum masuk ke mode wsl
> {: .prompt-info }

| Command  | Descriptions |
| -------- | ------------ |
| wslfetch |              |
| pwd      |              |
| whoami   |              |

> **NOTE:** Perintah diatas digunakan setelah masuk ke mode wsl
> {: .prompt-info }

#### Running ubuntu command with wsl

- tanpa masuk dulu mode linux
- tambahkan `wsl` sebelum kode perintah under linuxnya
  - *Ex: Cek status ssh* `wsl service ssh status`

#### WSL Packages & Services

| Command                                | Descriptions                                      |
| -------------------------------------- | ------------------------------------------------- |
| sudo nano /etc/apt/sources.list        |                                                   |
| sudo apt update                        |                                                   |
| sudo apt full-upgrade                  |                                                   |
| sudo apt-get purge --auto-remove gedit | ..                                                |
| code .                                 | vscode wsl remote, _using code on windows system_ |

> by default `systemctl` was disable because system has not been booted with systemd as init system.
> gunakan perintah `service` to check services on wsl, misalkan `service ssh status`, kalo mau dari powershell `wsl service ssh status`
> {: .prompt-info }

> kalo ada error ssh gak bisa di start, update dan upgrade dulu, `sudo apt update && sudo apt upgrade` {: .prompt-info }

| Command                    | Descriptions                       |
| -------------------------- | ---------------------------------- |
| service --status-all       | display all services on ubuntu wsl |
| service ssh status         | cek status sshd                    |
| sudo service ssh start     | start sshd                         |
| sudo service ssh stop      | stop sshd                          |
| service ssh --full-restart | restard sshd                       |

#### System Informations

| Command              | Descriptions                                                          |
| -------------------- | --------------------------------------------------------------------- |
| lscpu                | display information about the CPU architecture                        |
| lshw                 | list hardware                                                         |
| du                   | Summarize disk usage of the set of FILEs, recursively for directories |
| df                   | report file system disk space usage                                   |
| **fdisk**            | **manipulate disk partition table**                                   |
| vmstat               | Report virtual memory statistics                                      |
| uptime               | uptime running pc                                                     |
| ip a                 | check ip address                                                      |
| ip addr              | check ip address                                                      |
| ip addr \| grep eth0 |                                                                       |

#### Manage Process

| Command       | Descriptions                                                                          |
| ------------- | ------------------------------------------------------------------------------------- |
| `echo $PATH`  | display path environment                                                              |
| `ps`          | displays information about a selection of the active processes, eg: `ps -e`, `pas -a` |
| `tree`        | list contents of directories in a tree-like format                                    |
| pidof -z sshd | List zombie and I/O waiting processes. May cause pidof to hang.                       |
| `pstree`      | Display a tree of processes                                                           |
| `top`         | display Linux processes with dynamic real-time view of a running system               |
| `htop`        | mostly like `top` interactive process viewer                                          |

#### Users & Groups

| Command                   | Descriptions                                                |
| ------------------------- | ----------------------------------------------------------- |
| cat /etc/passwd           |                                                             |
| useradd                   | create user only                                            |
| usermod                   | create user only                                            |
| userdel                   | create user only                                            |
| adduser                   | create user also create /home/jack, eg: `sudo adduser jack` |
| `usermod`                 | mod jack as group sudo `sudo usermod -aG sudo jack`         |
| cat /etc/passwd           |                                                             |
| groupadd                  | *groupadd marketing accounting*                             |
| groupmod                  | *groupmod -n marketing old_group*                           |
| groupdel                  |                                                             |
| `gpasswd`                 | *administer /etc/group and /etc/gshadow*                    |
| gpasswd -a jack marketing | *add jack to group marketing*                               |

#### Permissions

| Command               | Descriptions                          |
| --------------------- | ------------------------------------- |
| su jack               | switch as jack in current session     |
| su - jack             | login to jack environment new session |
| sudo cat /etc/sudoers | use `sudo visudo` to modify           |

#### Working with Files and Directories

| Command | Descriptions                        |
| ------- | ----------------------------------- |
| ls      | list dir                            |
| cd      | change dir                          |
| \|      | pipe                                |
| less    | eg: <mark> ls /etc/ \| less </marK> |
| more    | eg: <mark> ls /etc/ \| more </marK> |

#### hash

| Command | Descriptions |
| ------- | ------------ |
| hash    |              |
| cksum   |              |
| find    |              |
| grep    |              |
| diff    |              |

#### Link

| Command                     | Descriptions                     |
| --------------------------- | -------------------------------- |
| ln file1 fileA              | hardlink file1 shortcutnya fileA |
| `ln -s folder1 sym-folder1` | simbolic link                    |

#### Compression

| Command | Descriptions                                      |
| ------- | ------------------------------------------------- |
| tar     | compress: tar -cvf tarball.tar file1 file2 file 3 |
|         | extract: tar -xf tarball.tar                      |
| gzip    | compress: gzip marketing.tar                      |
|         | extract: gzip -d marketing.tar.gz                 |
| zip     | zip -r [foldername]                               |
|         | unzip [foldername]                                |

#### Manage Log

| Command                      | Descriptions |
| ---------------------------- | ------------ |
| lastlog                      |              |
| ls /var/log                  |              |
| cat /var/log/apt/history.log | grep purge   |

#### SSH to AWS EC2

- using `key.pem` method

  ```bash
  sudo ssh -i /path/to/key.pem username@<remote_host_ip>
  ```

### LAMPP

> Linux Apache PHP MySql PHP PhpMyAdmin

### Apache

### PHP

### MySql

### PhpMyAdmin

### Network

#### Mengganti hostname

hostname
hostnamectl
hostnamectl set-hostname <new-hostname>
sudo nano /etc/hosts

**permanent** :
`sudo nano /etc/wsl.conf`
```
[network]
hostname = DemoHost
generateHosts = false
generateResolvConf = false
``` 
- `wsl --list --running`
- `wsl --shutdown`
  
  **Atau** `wsl --terminate Ubuntu`

### Install Packages untuk Belajar

#### Install NodeJS

1. Install NVM (Node Version Manager)

   - <https://docs.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-on-wsl>

   > Or See this post: [posts/nvm/](/posts/nvm/)
   > {: .prompt-info }
