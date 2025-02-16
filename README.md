# VS Code in Browser - Code Server

This repository helps you run **VS Code in your browser** using [`code-server`](https://github.com/coder/code-server). With this setup, you can access VS Code from anywhere on any device.

## Features
- Run **VS Code in a web browser**.
- Works on **Linux, Windows, macOS, and Android**.
- Access your development environment remotely.
- Supports **extensions, themes, and customization**.
- Lightweight and fast.

## Installation
Follow the steps below to install `code-server` on your device.

### 🖥️ Linux (Debian/Ubuntu)
```bash
# Update and install dependencies
sudo apt update && sudo apt install -y curl

# Download and install code-server
curl -fsSL https://github.com/coder/code-server/releases/latest/download/code-server.deb -o code-server.deb
sudo dpkg -i code-server.deb

# Start code-server
code-server
```

### 🖥️ Linux (Arch)
```bash
# Install code-server from AUR
yay -S code-server

# Start code-server
code-server
```

### 🍏 macOS
```bash
# Install using Homebrew
brew install code-server

# Start code-server
code-server
```

### 🖥️ Windows
#### Using Chocolatey:
```powershell
choco install code-server
```
#### Using Scoop:
```powershell
scoop install code-server
```
#### Manual Download:
1. Download the latest `code-server` from [Releases](https://github.com/coder/code-server/releases).
2. Extract and run `code-server.exe`.

### 📱 Android (via Termux)
```bash
# Update and install dependencies
pkg update && pkg install -y curl

# Download and install code-server
curl -fsSL https://github.com/coder/code-server/releases/latest/download/code-server-linux-arm64.tar.gz -o code-server.tar.gz
tar -xvzf code-server.tar.gz
cd code-server-*
./code-server
```

## Usage
After installation, start the server with:
```bash
code-server
```
You will see an output like:
```
info  Server listening on http://127.0.0.1:8080
info  - Password: 123456
info  - To disable password, use --auth none
```
Now open `http://127.0.0.1:8080` in your browser and enter the password.

## Configuration
Modify the configuration file at:
```bash
~/.config/code-server/config.yaml
```
To disable password authentication:
```yaml
auth: none
```
To change the port:
```yaml
bind-addr: 0.0.0.0:8080
```
Restart code-server for changes to apply:
```bash
systemctl restart code-server
```

## Running as a Service (Linux)
```bash
sudo systemctl enable --now code-server
```
To check status:
```bash
systemctl status code-server
```

## Updating code-server
To update to the latest version:
```bash
curl -fsSL https://github.com/coder/code-server/releases/latest/download/code-server.deb -o code-server.deb
sudo dpkg -i code-server.deb
```

## Uninstall
### Linux
```bash
sudo apt remove --purge code-server
```
### macOS
```bash
brew uninstall code-server
```
### Windows
```powershell
choco uninstall code-server
```

## Troubleshooting
### Port Already in Use
Change the port:
```bash
code-server --bind-addr 0.0.0.0:9000
```

### Permission Issues
Run as root:
```bash
sudo code-server
```

## Contributing
Feel free to contribute by submitting issues and pull requests.

## License
This project is licensed under the [MIT License](LICENSE).

