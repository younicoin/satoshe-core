# Linux Node Wallet Installation Guide

[!] Before start, make sure you have Ubuntu version 20.04 or higher installed and then follow the tutorial.
  
### Step №1.

Update your Ubuntu server:

```
sudo apt-get update && sudo apt-get upgrade -y
```

> **If you have Ubuntu version 20.04**, you will need to upgrade to GLIBC version >=2.34. 

```
apt update && apt upgrade
echo "deb http://cz.archive.ubuntu.com/ubuntu jammy main" >> /etc/apt/sources.list && apt update && apt install tmux -y && apt install libc6 -y
```

Answer yes to any question to complete installation.

### Step №2.

Download the Linux daemon and tools for your walle:

```
wget "" -O satoshe-1.0.0-linux.tar.gz
```

### Step №3.

Extract the .tar file:

```
tar -xzvf satoshe-1.0.0-linux.tar.gz
```

### Step №4.

Type the following command to install the daemon and tools for your wallet:

```
sudo mv satoshed satoshe-cli satoshe-tx /usr/bin/
```

### Step №5.

Create the data directory for your coin with the following command:

```
mkdir $HOME/.satoshe
```

### Step №6.

Create new **satoshe.conf** with nano

```
nano $HOME/.satoshe/satoshe.conf -t
```

and paste the following text.

```
rpcuser=ANY_USERNAME
rpcpassword=ANY_PASSWORD
rpcbind=127.0.0.1
rpcallowip=127.0.0.1
listen=1
server=1
txindex=1
daemon=1
addnode=82.148.2.179
addnode=82.97.246.156
addnode=37.220.83.16
```

Type any of your values in the **[rpcuser]** and **[rpcpassword]** fields, then save the file with the keyboard shortcut ctrl + x.

### Step №7.

Type the following command to start your node:

```
satoshed -daemon
```

### Optional wallet commands.

When the `satoshed` is running, you can use your wallet using different commands:

- `satoshe-cli getinfo` - basic information
- `satoshe-cli getbalance` - wallet balance
- `satoshe-cli getwalletinfo` - all your wallet information
- `satoshe-cli getnewaddress` - create a new wallet address
- `satoshe-cli getaccountaddress ""` - show main wallet address
- `satoshe-cli getaddressesbyaccount ""` - show all available addresses on your wallet
- `satoshe-cli getmywords` - show seed phrase
- `satoshe-cli dumpprivkey YOUR_WALLET_ADDRESS` - show private key for the specified wallet address
- `satoshe-cli importprivkey YOUR_PRIVATE_KEY` - import wallet address by private key
