# Linux Commands

A curated list of essential Linux commands with brief explanations and common options.  
Perfect for quick reference or as a study guide.

---

## Basic Commands

| Command | Description | Notes |
|---------|-------------|-------|
| `pwd` | Print current working directory | **p**rint **w**orking **d**irectory |
| `ls` | List directory contents | |
| `cd ../[dir]` | Change directory | `..` = parent directory |
| `sudo [command]` | Execute command with superuser privileges | |
| `cat /etc/passwd` | Display user accounts | |
| `sudo cat /etc/shadow` | Display password hashes (requires root) | |
| `whoami` | Show current username | |
| `cat [file]` | Concatenate (display) file contents | |
| `cp [source] [dest]` | Copy files or directories | |
| `rm [file]` | Remove files or directories | Use `-r` for directories |
| `which [command]` | Show full path of a command | e.g., `which ls` → `/bin/ls` |

---

## System Information

| Command | Description | Notes |
|---------|-------------|-------|
| `ps` | List running processes | **p**rocess **s**tatus |
| `id` | Display user and group IDs | |
| `hostname` | Show system hostname | |
| `uname -a` | Show all system information | **un**ix **name**, `-a` = all |
| `uname -r` | Show kernel release | `-r` = kernel release |
| `who` | Show who is logged in | |

---

## Network Commands

| Command | Description | Notes |
|---------|-------------|-------|
| `ifconfig` | Configure network interfaces (deprecated) | Often replaced by `ip` |
| `ip a` | Show IP addresses and interfaces | `ip addr` |
| `netstat` | Network statistics and connections | |
| `curl [url]` | Transfer data from/to a server | |
| `curl -I [url]` | Fetch HTTP headers only | `-I` = headers |
| `curl -v [url]` | Verbose output (includes headers) | `-v` = verbose |

---

## Hardware Information

| Command | Description | Notes |
|---------|-------------|-------|
| `lsblk` | List block devices (hard drives, partitions) | |
| `lsusb` | List USB devices | |
| `lsof` | List open files and processes | |

---

## Help & Manuals

| Command | Description | Notes |
|---------|-------------|-------|
| `man [command]` | Display manual page for a command | |
| `[command] -h` or `--help` | Show brief help | Many commands support this |
| `apropos [keyword]` | Search command names and descriptions | Useful when you forgot a command |

---

## User Management

| Command | Description | Notes |
|---------|-------------|-------|
| `sudo adduser [username]` | Add a user with interactive prompts | |
| `sudo useradd [username]` | Add a user with default settings (no home dir) | |
| `sudo useradd -m [username]` | Add a user and create home directory | `-m` = create home |
| `sudo userdel [username]` | Delete a user | |
| `sudo usermod [options] [username]` | Modify a user account | See `man usermod` |
| `sudo passwd [username]` | Change user's password | |
| `su -` | Switch to root user | `-` loads root's environment |
| `su - [username]` | Switch to another user | |
| `exit` or `logout` or `Ctrl+D` | Exit current shell / logout | |
| `sudo visudo` | Edit sudoers file safely | |
| `sudo groupadd [group]` | Create a new group | |
| `groups [username]` | Show groups a user belongs to | |
| `sudo usermod -aG [group] [user]` | Add user to a group | `-a` = append, `-G` = supplementary groups |
| `sudo gpasswd -d [user] [group]` | Remove user from a group | `-d` = delete |

---

## Package Management (APT & dpkg)

| Command | Description | Notes |
|---------|-------------|-------|
| `sudo dpkg -i [package.deb]` | Install a local `.deb` file | `-i` = install |
| `sudo apt install [package]` | Install package from repositories | |
| `sudo apt purge [package]` | Remove package and its configuration files | |
| `sudo apt update && sudo apt upgrade` | Update package lists and upgrade all packages | |
| `apt list --installed \| grep [pattern]` | List installed packages and filter | Use `dpkg -l` as alternative |

---

## Daemons / Services (systemd)

| Command | Description | Notes |
|---------|-------------|-------|
| `sudo systemctl enable [service]` | Enable service to start at boot | |
| `sudo systemctl disable [service]` | Disable service from starting at boot | |
| `sudo systemctl start [service]` | Start a service immediately | |
| `sudo systemctl stop [service]` | Stop a service immediately | |
| `sudo systemctl restart [service]` | Restart a service | |
| `sudo systemctl reload-or-restart [service]` | Reload or restart (if reload not supported) | |
| `sudo systemctl status [service]` | Show service status | |
| `sudo systemctl is-active [service]` | Check if service is active (running) | |
| `sudo systemctl is-enabled [service]` | Check if service is enabled at boot | |
| `sudo systemctl list-units` | List all loaded units | |
| `sudo systemctl list-units -t [type]` | Filter by unit type (e.g., service, socket) | `-t` = type |
| `sudo systemctl list-unit-files \| grep [pattern]` | List all unit files and their enable status | |

---

## Process Management

| Command | Description | Notes |
|---------|-------------|-------|
| `ps aux` | List all running processes | `a` = all users, `u` = user-oriented, `x` = processes without terminal |
| `ps -u [user] \| grep [process]` | List processes for a user and filter | |
| `pgrep [process]` | Find process IDs by name | **p**s + **grep** |
| `kill [PID]` | Terminate a process by ID | Default signal = SIGTERM (15) |
| `kill -l` | List all signal names | |
| `kill -19 [PID]` | Stop (pause) a process | Signal 19 = SIGSTOP (like Ctrl+Z) |
| `kill -2 [PID]` | Interrupt a process | Signal 2 = SIGINT (like Ctrl+C) |
| `pkill -9 [name]` | Kill all processes matching name with SIGKILL | Signal 9 = SIGKILL (force) |
| `top` | Interactive process viewer | |
| `htop` | Enhanced interactive process viewer | (may need installation) |
| `jobs` | List background jobs in current shell | |
| `bg [job]` | Resume a stopped job in background | |
| `fg [job]` | Resume a stopped job in foreground | |
| `ping -c [count] [host]` | Send ICMP echo requests | `-c` = count |
| `sleep 30` | Sleep for 30 seconds (foreground) | |
| `ping -c 4 google.com &` | Run command directly in background | `&` at end |

---

## Web / One‑Line Servers

| Command | Description | Notes |
|---------|-------------|-------|
| `python -m http.server` | Start a simple HTTP server on port 8000 | `-m` = run module |
| `php -S [ip]:[port]` | Start PHP built-in web server | `-S` = server |
| `npx http-server -p [port]` | Run a temporary HTTP server using npx | npx downloads & runs the package |
| `curl [url]` | Fetch webpage content | |
| `curl -o [filename] [url]` | Download file and save with custom name | `-o` = output |
| `curl -I [url]` | Fetch only HTTP headers | |
| `curl -v [url]` | Verbose output (includes request/response headers) | |

---

## Notes

- Commands assume a Debian/Ubuntu environment (APT package manager).
- Some commands may require installation (e.g., `htop`, `npx`).
- Use `man [command]` for detailed documentation.

---

Feel free to contribute improvements or report issues!
