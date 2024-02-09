# Compiling Windows Source Guide

Let's compile a wallet for Windows on Ubuntu Server 20.04 and higher with the following tutorial.

### Step №1.

Update your Ubuntu server:

```
sudo apt-get update && sudo apt-get upgrade -y
```

### Step №2.

Install the required dependencies:

```
sudo apt-get install make automake cmake curl g++-multilib libtool binutils-gold bsdmainutils pkg-config python3 patch bison g++-mingw-w64-x86-64 -y
```

> **If you have Ubuntu version 20.04**, you will need to upgrade to GLIBC version >=2.34. 

```
apt update && apt upgrade
echo "deb http://cz.archive.ubuntu.com/ubuntu jammy main" >> /etc/apt/sources.list && apt update && apt install tmux -y && apt install libc6 -y
```

Answer yes to any question to complete installation.

### Step №3.

Create your source code directory:

```
cd ~/
mkdir satoshe-src-win
cd satoshe-src-win
```

And download the source code of **SOSHE** with the following command:

```
git clone https://github.com/SatosheNetwork/satoshe-core.git .
```

### Step №4 (Build 64-bit ver)

Build x86_64-satoshe windows version with the following commands:

```
sudo update-alternatives --set x86_64-w64-mingw32-g++ /usr/bin/x86_64-w64-mingw32-g++-posix
```

```
PATH=$(echo "$PATH" | sed -e 's/:\/mnt.*//g')
cd depends
sudo make HOST=x86_64-w64-mingw32
cd ..
```

### Step №5

Type the following commands to compile your wallet for Windows.

```
./autogen.sh
CONFIG_SITE=$PWD/depends/x86_64-w64-mingw32/share/config.site ./configure --prefix=/
make
```

> The compiled wallet for Microsoft Windows is located in the directory `src/qt`, the tools are located in the directory `src`.


