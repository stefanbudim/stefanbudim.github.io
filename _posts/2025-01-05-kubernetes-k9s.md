---
title: "K9s - A Simplified Kubernetes Management Tool"
categories: [Kubernetes, k9s]
tags: [kubernetes,productivity]     # TAG names should always be lowercase
---
K9s will bring your productivity to next level.
Similar to
- [LazyDocker Post]({% post_url 2025-01-05-docker-lazydocker %}) / [LazyDocker](https://github.com/jesseduffield/lazydocker) for Docker
- [MidnightCommander](https://midnight-commander.org/)/[TotalCommander](https://www.ghisler.com/) File Manager
- [Lazygit](https://github.com/jesseduffield/lazygit) Git-Client

With few keyboard strokes you get in one second an overview of kubernetes resources. With one click or keystroke you can view the logs, open a shell, stop/start a container, track in real-time activities of resources or do live updates during troubleshooting.

## K9s: A Simplified Kubernetes Management Tool

If you're a developer working with Kubernetes, you know how powerful yet sometimes cumbersome it can be to manage kubernetes resources from the command line. That's where **K9s** comes in — a simple, user-friendly terminal UI. While tools like kubectl provide powerful capabilities, they can feel overwhelming for day-to-day cluster management tasks.

### What is [K9s](https://k9scli.io/)?
K9s is a terminal based UI to interact with your Kubernetes clusters. The aim of this project is to make it easier to navigate, observe and manage your deployed applications.


### Key Features of K9s:
- **Information At Your Finger Tips**: Tracks in real-time activities of resources running in your Kubernetes cluster.
- **Container Management**: View and manage running containers, start/stop/restart them, and monitor their stats in real-time.
- **Live Updates**: Automatically refreshes resource views, saving time during troubleshooting.
- **Context Switching**: Easily switch between different namespaces or clusters.
- **Standard or CRD?** : Handles both Kubernetes standard resources as well as custom resource definitions.
- **Cluster Metrics**: Tracks real-time metrics associates with resources such as pods, containers and nodes.
- **Power Users Welcome!**: Plugin support to extend K9s to create your very own cluster commands. Provides standard cluster management commands such as logs, scaling, port-forwards, restarts…Powerful filtering mode to allow user to drill down and view workload related resources.
- **RBAC**: Supports for viewing RBAC rules such as cluster/roles and their associated bindings. Reverse lookup to asserts what a user/group or ServiceAccount can do on your clusters.
- **Built-in Benchmarking**: You can benchmark your HTTP services/pods directly from K9s
- **Resource Management**: Quickly list, edit, delete, or describe Kubernetes resources.
- **Resource Graph Traversals**: K9s provides for easy traversal of Kubernetes resources and their associated resources.
- **Log Monitoring**: Easily tail the logs of any container with a simple command.
- **Cross-Platform Support**: K9s works on Linux, macOS, and Windows.

### Why Use K9s?

- **Time Saver**: Provides a fast and easy way to interact with Kubernetes without needing to memorize long commands.
- **No GUI Required**: It’s a terminal-based UI, which means it works even on servers or headless systems where a GUI might not be available.
- **User-Friendly**: It is a lightweight and intuitive tool designed for users who want to spend less time managing.


## Installing K9s
Linux:
```bash
curl -sS https://webinstall.dev/k9s | bash
```

Arch/Manjaro:
```bash
yay -S k9s
```

With Docker
```bash
docker run --rm -it -v \
/var/run/docker.sock:/var/run/docker.sock \
-v /yourpath:/.config/jesseduffield/K9s \
lazyteam/K9s
```

Windows:
```bash
scoop install k9s
```


MacOS:
```bash
brew install derailed/k9s/k9s
```


## Using K9s
### Start K9s
```bash
k9s
```
This command launches the K9s interface. By default, it will connect to the current Kubernetes context set by kubectl. From there, you can:
- Use arrow keys to navigate resources.
- Press / to filter resources.
- Use :q to quit the application.


### Common Shortcuts

| Shortcuts | Action                           |
| --------- | -------------------------------- |
| **?**     | Show help and keyboard shortcuts |
| **q**     | Quit K9s                         |
| **/**     | Search/filter resources.         |
| **d**     | Describe a selected resource.    |
| **l**     | View logs for a selected pod.    |
| **x**     | Delete a resource.               |
| **0-9**   | Switch between resource views.   |


### The Terminal UI looks like a Dashboard
A top level dashboard of the state of your cluster
![K9s Terminal UI](/assets/img/k9s/k9s-dashboard.png)
Pods - List out your pods status and resource consumption
![K9s Terminal UI](/assets/img/k9s/k9s-pods-status-resource-consumption.png)
Logs - View and interact with your container logs
![K9s Terminal UI](/assets/img/k9s/k9s-logs.png)
Dig in your cluster resources and view their dependencies
![K9s Terminal UI](/assets/img/k9s/k9s-cluster-resource-dependencies-view.png)
RBAC - View the who/what/how of authorizations on your cluster
![K9s Terminal UI](/assets/img/k9s/k9s-rbac.png)


Ready to simplify your Kubernetes management? Give K9s a try today!
