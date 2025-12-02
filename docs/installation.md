---
title: "Installation"
sidebar_position: 2
slug: /installation
---


## Full Installation (Ambrosia + phoenixd)

```bash
wget -q https://raw.githubusercontent.com/olympus-btc/Ambrosia-POS/master/scripts/install.sh
chmod +x install.sh
./install.sh
```

The phoenixd installation script installs phoenixd automatically. The script downloads phoenixd v0.7.1, verifies the package integrity using GPG and checksums, installs it in `/usr/local/bin`, and optionally configures a systemd service for automatic startup.


## Project Instalation (without systemd)
```bash
curl -fsSL https://raw.githubusercontent.com/olympus-btc/Ambrosia-POS/master/scripts/install.sh | bash
```

## Uninstallation 

To uninstall Ambrosia POS and phoenixd, run the following script:

```bash
curl -fsSL https://raw.githubusercontent.com/olympus-btc/Ambrosia-POS/master/scripts/uninstall.sh | bash
```
