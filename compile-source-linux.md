# Compiling Linux source guide

Let's compile a wallet for Ubuntu/Linux on Ubuntu Server 20.04 and abobe with the following tutorial.

### Step №1.

Update your Ubuntu server:

```
sudo apt-get update && sudo apt-get upgrade -y
```

### Step №2.

Install the required dependencies:

```
sudo apt-get install git make automake cmake curl g++-multilib libtool binutils-gold bsdmainutils pkg-config python3 patch bison -y
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
mkdir satoshe-src
cd satoshe-src
```

And download the source code of your coin with the following command:

```
git clone https://github.com/SatosheNetwork/satoshe-core.git .
```

### Step №4-1 (Build 64-bit ver)

Build x86_64-linux-gnu version with the following commands:

```
PATH=$(echo "$PATH" | sed -e 's/:\/mnt.*//g')
cd depends
sudo make HOST=x86_64-pc-linux-gnu
cd ..
```

Type the following commands to compile your wallet for Ubuntu Linux.

```
./autogen.sh
CONFIG_SITE=$PWD/depends/x86_64-pc-linux-gnu/share/config.site ./configure --prefix=/
sudo make
```

Type the following command to clean your source code:

```
make clean
```

### Step №4-2 (Build 32-bit ver)

Build x86_linux-gnu version with the following commands:

```
PATH=$(echo "$PATH" | sed -e 's/:\/mnt.*//g')
cd depends
sudo make HOST=i686-pc-linux-gnu
cd ..
```

### Step №5

Type the following commands to compile your wallet for Ubuntu Linux.

```
./autogen.sh
CONFIG_SITE=$PWD/depends/i686-pc-linux-gnu/share/config.site ./configure --prefix=/
sudo make
```

> The compiled wallet for Ubuntu Linux is located in the directory `src/qt`, the tools are located in the directory `src`.


