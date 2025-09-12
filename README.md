# SSH Server Commands 💻

[![License](https://img.shields.io/github/license/der-programmer1/ssh-server-commands)](https://github.com/der-programmer1/ssh-server-commands)
[![GitHub Repo stars](https://img.shields.io/github/stars/der-programmer1/ssh-server-commands?style=social)](https://github.com/der-programmer1/ssh-server-commands/stargazers)

Quick and easy guide to set up, secure, and use SSH servers on **Linux**, **Mac**, and **Windows**. Perfect for beginners and anyone who wants a copy-paste solution.

---

## Table of Contents
- [Linux Setup](#linux-setup-🐧)
- [Mac Setup](#mac-setup-🍎)
- [Windows Setup](#windows-setup-🖥️)
- [Basic Commands](#basic-commands-📋)
- [SSH Keys & Security](#ssh-keys--security-🔑)
- [Tips & Tricks](#tips--tricks-💡)

---

## Linux Setup 🐧

Install OpenSSH and start the server:

```bash
sudo apt update && sudo apt install -y openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh
ip addr show   # Check your IP address
```

Connect from another machine:

```bash
ssh username@your_ip
```

Check service status:

```bash
sudo systemctl status ssh
```

---

## Mac Setup 🍎

OpenSSH is usually pre-installed. Enable Remote Login:

```bash
sudo systemsetup -setremotelogin on
whoami          # Check your username
ifconfig        # Check your IP address
```

Connect from another machine:

```bash
ssh username@your_ip
```

---

## Windows Setup 🖥️

1. Install OpenSSH Server:  
   Settings → Apps → Optional Features → Add OpenSSH Server
2. Start and enable the service:

```powershell
Start-Service sshd
Set-Service -Name sshd -StartupType 'Automatic'
```

3. Check IP:

```powershell
ipconfig
```

Connect from another machine:

```bash
ssh username@your_ip
```

---

## Basic Commands 📋

| Task | Command |
|------|---------|
| Create a file | `nano <filename>` |
| Read a file | `cat <filename>` |
| Edit a file | `nano <filename>` |
| List files | `ls -lah` |
| Change directory | `cd <directory>` |
| Show current directory | `pwd` |
| Run admin commands | `sudo <command>` |
| Switch user | `su - <username>` |
| Zip a file | `zip archive.zip <files>` |
| Unzip a file | `unzip <file.zip>` |
| View zip content | `unzip -p <file.zip> | less` (press `q` to exit) |

> ⚠️ Tip: Always copy-paste commands carefully and understand what they do.

---

## SSH Keys & Security 🔑

Generate SSH keys for passwordless login:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
ssh-copy-id username@remote_ip
```

Disable root login (Linux only):

```bash
sudo nano /etc/ssh/sshd_config
# Set: PermitRootLogin no
sudo systemctl restart ssh
```

Firewall tips:

- Only allow port 22 for trusted networks.
- Consider changing SSH port for extra security.

---

## Tips & Tricks 💡

- Use emojis for OS clarity: 🍎 Mac, 🖥️ Windows, 💻 Linux
- Add screenshots or GIFs for key steps to improve readability
- Encourage users to open Issues or Discussions for help
- Keep commands short and copy-paste ready

---

Made with ❤️ by [der-programmer1](https://github.com/der-programmer1)
