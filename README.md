# SideServer for Linux

_`SideServer-for-Linux` is a fork of [AltLinux](https://github.com/i-love-altlinux/AltLinux) that allows to easily install SideStore or any sideload apps onto an iPhone, an iPad, or iPod Touch._

> Direct sideloading supports iOS 12.2 and later, while `SideStore` supports iOS 14.0 and later.

[![Pylint](https://github.com/SideStore/SideServer-for-Linux/actions/workflows/pylint.yml/badge.svg)](https://github.com/SideStore/SideServer-for-Linux/actions/workflows/pylint.yml)

![Alt](https://repobeats.axiom.co/api/embed/835f4c1978a060e579fc45aedcdf43467bc42f02.svg "Repobeats analytics image")

## Features:

  - A straight-forward GUI
  - A tray menu that works just like on Windows
  - Sideloading SideStore directly
  - Sideloading apps independently of SideStore
  - While the tray icon is present, SideServer runs in the background in tethered mode for USB connections (which is only needed if you don't have access to WiFi)

If you're experiencing issues or want to help, you can join the [SideStore Discord](https://discord.gg/sidestore-949183273383395328).

## Installing SideServer

SideServer is available for Ubuntu 22.04 and Ubuntu 20.04.

Derivatives, such as Linux Mint and Pop!_ OS should also work. To make sure which DEB package to pick, run the following command:

```bash
python3 --version
```

| Python 3.10          | Python 3.8        |
|:--------------------:|:-----------------:|
| Ubuntu 22.04         | Ubuntu 20.04      |
| Pop!_OS 22.04        | Pop!_OS 20.04     |
| Linux Mint 21        | Linux Mint 20     |
| elementary OS 7      | elementary OS 6   |
| Zorin OS 17          | Zorin OS 16       |

If you're running Ubuntu 22.04 or any distro based on it (such as Mint 21), install the DEB package from [here](https://github.com/SideStore/SideServer-for-Linux/releases).

If you're running Ubuntu 20.04 or any distro based on it (such as Mint 20), run the following commands:

```bash
sudo add-apt-repository ppa:apandada1/libhandy-1
sudo apt update
sudo apt install libhandy-1-0 libhandy-1-dev
```

Then you can install the DEB package [from here](https://github.com/SideStore/SideServer-for-Linux/releases).

If you use Fedora, you can [run the script without installing](#run-the-script-without-installing).

## Uninstalling SideServer

If you want to uninstall SideServer, run the following commands:

```bash
sudo apt purge altlinux
sudo rm -rf /usr/lib/altlinux
rm -rf $HOME/.local/share/altlinux
```

## Run the script without installing

### Ubuntu:

Add the `universe` repository:

```bash
sudo add-apt-repository universe -y
```

Install the dependencies:

```bash
sudo apt-get install binutils python3-pip git gir1.2-appindicator3-0.1 usbmuxd libimobiledevice6 libimobiledevice-utils wget curl libavahi-compat-libdnssd-dev zlib1g-dev unzip usbutils
```

IF YOU'RE RUNNING UBUNTU 20.04 OR ITS [DERIVATIVES](https://github.com/SideStore/SideServer-for-Linux#install-altlinux):

```bash
sudo add-apt-repository ppa:apandada1/libhandy-1
sudo apt update
sudo apt install libhandy-1-0 libhandy-1-dev
```

Run the following commands:

```bash
git clone https://github.com/SideStore/SideServer-for-Linux
cd "SideServer-for-Linux"
python3 main.py
```

### Fedora:

Install the dependencies:

```bash
sudo dnf install binutils python3-pip git libappindicator-gtk3 usbmuxd libimobiledevice-devel libimobiledevice-utils wget curl avahi-compat-libdns_sd-devel dnf-plugins-core unzip usbutils
```

Clone and build:

```bash
git clone https://github.com/SideStore/SideServer-for-Linux
cd "SideServer-for-Linux"
python3 main.py
```

### Arch Linux

Install the dependencies:
```bash
sudo pacman -S binutils wget curl git python-pip libappindicator-gtk3 usbmuxd libimobiledevice avahi zlib unzip usbutils libhandy
```

Clone and build:

```bash
git clone https://github.com/SideStore/SideServer-for-Linux
cd "SideServer-for-Linux"
python3 main.py
```

## Compile the DEB package
Add the `universe` repository:

```bash
sudo add-apt-repository universe -y
```

Install the dependencies:

```bash
sudo apt-get install binutils python3-pip git gir1.2-appindicator3-0.1 usbmuxd libimobiledevice6 libimobiledevice-utils wget curl libavahi-compat-libdnssd-dev zlib1g-dev unzip usbutils
```

If you're running Ubuntu 20.04 or any distro based on it (such as Mint 20), run the following commands:

```bash
sudo add-apt-repository ppa:apandada1/libhandy-1
sudo apt update
sudo apt install libhandy-1-0 libhandy-1-dev
```

Install pyinstaller:

```bash
pip3 install pyinstaller
```

Reboot your computer for changes to take effect.

After that, proceed by running the following commands:

```bash
git clone https://github.com/SideStore/SideServer-for-Linux
cd "SideServer-for-Linux"
./build.sh
```

The DEB file is ready! You can install it now.

## Credits

AltLinux created by [maxasix](https://github.com/yourfriendoss)

AltServer-Linux made by [NyaMisty](https://github.com/NyaMisty)

Artwork by [Nebula](https://github.com/itsnebulalol)

Provision by [Dadoum](https://github.com/Dadoum)
