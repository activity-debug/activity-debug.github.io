---
title: Node Version Manager on WSL
description: Halaman ini akan di update seiring ada perubahan pada catatan yang saya buat
author: admin
date: 2024-10-24 18:30:21 +0700
categories: [Notes]
tags: [tags]
---

> Halaman ini akan di update seiring ada perubahan pada catatan yang saya buat
{: .prompt-info }

## Node Version Manager on WSL

> ini untuk ubuntu, wsl atau multipass dan sebangsanya, untuk windows disini [^Win]
{: .prompt-info }

### Requirement
```sh
which curl
# if not installed:
# sudo apt install curl
```

### Download Installer to home

```sh
cd ~

curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```

### Reload `.bashrc`
```sh
source ~/.bashrc
```

### Usefull Command

| command               | description                     |
| --------------------- | ------------------------------- |
| nvm                   | show manual page                |
| nvm list              | show available list             |
| nvm ls_remote \| less | show all available list         |
| nvm install lts       | install last lts                |
| nvm -v                | cek versi nvm                   |
| node -v               | cek versi node                  |
| npm -v                | cek versi npm                   |
| nvm use lts           | gunakan versi lts yg terinstall |

---

[^Win]: View on [Microsoft Docs](https://docs.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-on-windows)