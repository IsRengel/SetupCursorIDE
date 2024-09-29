# Setup: Install Cursor IA Code Editor on Linux

## Introduction

This guide helps you install **Cursor IA Code Editor** as a desktop application on Linux operating systems, regardless of which distribution you use, simplifying the setup process.

### What is Cursor IA Code Editor?

Cursor IDE is an AI-powered code editor, built on the foundations of Visual Studio Code and enhanced with ChatGPT integration. It offers a rich development experience with AI-based coding assistance. To learn more about Cursor IDE, visit the official [Cursor website](https://cursor.sh/).

<p align="center"> <a href="https://cursor.sh/"> <img src="./assets/cursor.png" alt="Cursor" width="100px"> </a> </p>

## Prerequisites

Before starting the installation, ensure the following dependencies are installed on your system:

- **Git**: Used to clone the repository.
- **Curl**: Required to download the installation files.
- **Bash**: The script is written in Bash, so ensure it's available in your shell.

To install these dependencies (if not already installed), use the following commands, depending on the distribution you use:

**Debian/Ubuntu y derivados**
```
sudo apt update
sudo apt install git curl bash -y

```

**Arch Linux/Manjaro/EndeavourOS**
```
sudo pacman -Sy
sudo pacman -S git curl bash --noconfirm

```

**Fedora**
```
sudo dnf install git curl bash -y

```

**OpenSUSE**
```
sudo zypper refresh
sudo zypper install git curl bash

```

**Gentoo**
```
sudo emerge --ask dev-vcs/git net-misc/curl app-shells/bash

```

**Solus**
```
sudo eopkg install -y git curl bash

```

## Installation

To install Cursor IDE, run the following command in your terminal. This will clone the repository, navigate into it, and start the installation process:

```
git clone https://github.com/argell10/InstallCursorEditorLinux.git --depth=1 && cd InstallCursorEditorLinux && ./install.sh && cd .. && rm -rf InstallCursorEditorLinux
```

This script will:

1. Download the Cursor IDE application.
2. Set it up as a desktop application.
3. Create a `.desktop` file for easy access from your applications menu.
4. Configure an automatic update script using `systemd`.
### Customizing the Installation

If you'd like to change the installation directory or other settings, you can modify the `install.sh` script before running it. The default installation path is `/opt/cursor/`.

## Features

- **AI-powered coding**: Leverages ChatGPT for real-time code suggestions and improvements.
- **Cross-platform**: Cursor IDE is available on Windows, macOS, and Linux.
- **VSCode-based**: Built on the familiar interface of Visual Studio Code, making it easy for VSCode users to adapt.

## Automatic Updates

The installation process configures a systemd service that checks for and installs the latest updates of Cursor IDE. To manually trigger an update, run the following command:

```
systemctl --user start update-cursor.service
```
To enable automatic updates at startup:
```
systemctl --user enable update-cursor.service
```

## Uninstallation

To completely remove Cursor IDE from your system, run:

```
sudo rm -rf /opt/cursor
rm ~/.config/systemd/user/update-cursor.service
```

Additionally, you can disable the systemd update service:

```
systemctl --user disable update-cursor.service
```

## Learn More

For more details about Cursor IDE and its features, visit the [official website](https://cursor.sh/).
