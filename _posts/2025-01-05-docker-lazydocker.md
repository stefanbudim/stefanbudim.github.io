---
title: "Lazydocker - A Simplified Docker Management Tool"
categories: [docker, lazydocker]
tags: [docker,productivity]     # TAG names should always be lowercase
---
Lazydocker will bring your productivity to next level.
Similar to
- [k9s](https://k9scli.io) for Kubernetes
- [MidnightCommander](https://midnight-commander.org/)/[TotalCommander](https://www.ghisler.com/) File Manager
- [Lazygit](https://github.com/jesseduffield/lazygit) Git-Client

With few keyboard strokes you get in one second an overview of running containers (Logs, CPU/Memory Usage, Env, Config, Top running processes). With one click or keystroke you can view the logs in an container, open a shell or stop/start a container.

## LazyDocker: A Simplified Docker Management Tool

If you're a developer working with Docker, you know how powerful yet sometimes cumbersome it can be to manage containers, networks, and volumes from the command line. That's where **LazyDocker** comes in — a simple, user-friendly terminal UI for managing Docker containers.

### What is [LazyDocker](https://github.com/jesseduffield/lazydocker)?

LazyDocker is an open-source tool that provides a **CLI-based GUI** for Docker management. It allows you to interact with your Docker environment more efficiently, offering a cleaner and faster way to view and manage containers, logs, volumes, networks, and even Docker Compose services, all within the terminal.

### Key Features of LazyDocker:
- **Container Management**: View and manage running containers, start/stop/restart them, and monitor their stats in real-time.
- **Log Monitoring**: Easily tail the logs of any container with a simple command.
- **Volume and Network Inspection**: View all volumes and networks, helping you better understand how your Docker setup is structured.
- **Docker Compose Support**: Directly manage and interact with services defined in `docker-compose.yml`.
- **Cross-Platform Support**: LazyDocker works on Linux, macOS, and Windows.

### Why Use LazyDocker?

- **Time Saver**: Provides a fast and easy way to interact with Docker without needing to memorize long commands.
- **No GUI Required**: It’s a terminal-based UI, which means it works even on servers or headless systems where a GUI might not be available.
- **User-Friendly**: It is a lightweight and intuitive tool designed for Docker users who want to spend less time managing and more time developing.


## LazyDocker vs [Portainer](https://www.portainer.io/)

| Feature                  | LazyDocker                             | Portainer                                  |
| ------------------------ | -------------------------------------- | ------------------------------------------ |
| **Type**                 | CLI-based Docker Management Tool       | Web-based Docker and Kubernetes Management |
| **Interface**            | Terminal (TUI - Text User Interface)   | Web Interface (GUI)                        |
| **Ease of Use**          | Requires familiarity with CLI          | Intuitive and beginner-friendly GUI        |
| **Installation**         | Lightweight, single binary             | Requires web server setup and container    |
| **Resource Usage**       | Minimal                                | Moderate (due to web interface overhead)   |
| **Features**             | Focused on Docker container management | Broad management for Docker & Kubernetes   |
| **Real-Time Monitoring** | Yes                                    | Yes                                        |
| **Logs and Stats**       | Yes, integrated into the TUI           | Yes, with rich visualization               |
| **Multi-Node Support**   | No                                     | Yes                                        |
| **User Management**      | Not available                          | Role-based access control                  |
| **Customization**        | Limited                                | High (integrates with plugins/extensions)  |
| **Use Case**             | Developers working in terminal         | Admins managing multiple servers and users |
| **Learning Curve**       | Low for CLI users                      | Low for GUI users                          |
| **Kubernetes Support**   | No                                     | Yes                                        |
| **Open Source**          | Yes                                    | Community edition is open source           |
| **Platform**             | Terminal-based                         | Browser-based                              |

**LazyDocker**: Best for developers who prefer managing Docker in a terminal environment with minimal resource usage.

**Portainer**: Ideal for teams or administrators managing multiple Docker/Kubernetes environments with an emphasis on user management and ease of use through a GUI.


## Installing LazyDocker
Linux:
```bash
curl -s https://api.github.com/repos/jesseduffield/lazydocker/releases/latest | jq -r .assets[0].browser_download_url | xargs wget -O lazydocker.deb && sudo dpkg -i lazydocker.deb
```

Arch/Manjaro:
```bash
yay -S lazydocker
```

With Docker
```bash
docker run --rm -it -v \
/var/run/docker.sock:/var/run/docker.sock \
-v /yourpath:/.config/jesseduffield/lazydocker \
lazyteam/lazydocker
```

MacOS:
```bash
brew install lazydocker
```


## Using Lazydocker
Start Lazydocker
```bash
lazydocker
```
The Terminal UI looks like a Dashboard
![Lazydocker Terminal UI](/assets/img/lazydocker/lazydocker-container-logs.png)
Navigate with [Keybindings](https://github.com/jesseduffield/lazydocker/blob/master/docs/keybindings/Keybindings_en.md) or with mouse.
![Lazydocker Terminal UI](/assets/img/lazydocker/lazydocker-container-stats.png)
![Lazydocker Terminal UI](/assets/img/lazydocker/lazydocker-container-env.png)
![Lazydocker Terminal UI](/assets/img/lazydocker/lazydocker-container-config.png)
![Lazydocker Terminal UI](/assets/img/lazydocker/lazydocker-container-top.png)
To get a list with all commands: Select an Object like a running container then press x:
![Lazydocker Terminal UI](/assets/img/lazydocker/lazydocker-container-cmds.png)

To open a shell in a running container: selected the Container, press x,  press E

To switch window use Tab or Shift-Tab or cursor left/right




![Lazydocker Terminal UI](/assets/img/lazydocker/lazydocker-container-cmds.png)
This is much faster than
```bash
docker exec -it <container_name_or_id> /bin/bash
```

Image Config
![Lazydocker Terminal UI](/assets/img/lazydocker/lazydocker-image-config.png)
Image Commands
![Lazydocker Terminal UI](/assets/img/lazydocker/lazydocker-image-cmds.png)
Volume Commands
![Lazydocker Terminal UI](/assets/img/lazydocker/lazydocker-volumes.png)
Network Commands
![Lazydocker Terminal UI](/assets/img/lazydocker/lazydocker-network.png)



