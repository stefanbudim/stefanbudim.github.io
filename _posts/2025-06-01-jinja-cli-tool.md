---
title: "Jinja from the command-line without python"
categories: [linux, kubernetes]
tags: [linux, kubernetes]     # TAG names should always be lowercase
---

[minijinja-cli](https://crates.io/crates/minijinja-cli) is a CLI tool to render [Jinja2](https://jinja.palletsprojects.com/en/stable/) templates.

Jinja2 is very powerfull for system admins to generate config files or kubernetes descriptors. Jinja2 dependends on python and python packages. In enterprise environments it can hurt to maintain these dependencies. minijinja-cli is a rust implementation of Jinja without such dependencies.

# Features
- single command line execution
- easy shell scripting
- steps in CI/CD pipelines with minimal overhead and setup
- fast template rendering as the Rust implementation is much faster than Python
- no dependencies required / no python required

# Usage

## To render a file

```bash
minijinja-cli service-template.j2 service-data.yaml \
> /etc/systemd/system/my.service
```
or

```bash
docker run --rm -v ".:/data" stefanbudim/minijinja-cli \
/data/service-template.j2 /data/service-data.yaml  > /etc/systemd/system/my.service
```
This will create file my.service
```bash
[Unit]
Description=My Custom Application Service
After=network.target

[Service]
Type=simple
ExecStart=/usr/bin/myapp --config /etc/myapp/config.yaml
Restart=on-failure
User=myappuser

[Install]
WantedBy=multi-user.target
```

Based on template and data files:

service-template.j2
```bash
[Unit]
Description={{ description }}
After=network.target

[Service]
Type=simple
ExecStart={{ exec_start }}
Restart=on-failure
User={{ user }}

[Install]
WantedBy=multi-user.target
```


service-data.j2
```bash
description: My Custom Application Service
exec_start: /usr/bin/myapp --config /etc/myapp/config.yaml
user: myappuser
```

More [examples](https://github.com/stefanbudim/minijinja-cli-docker/tree/main/examples)


[Generating Kubernetes YAML Files with Jinja2 Templates](https://github.com/stefanbudim/minijinja-cli-docker/blob/main/examples/kubernetes/README.md)


# Installation
- [minijinja-cli](https://crates.io/crates/minijinja-cli)
- [minijinja-cli-docker](https://hub.docker.com/r/stefanbudim/minijinja-cli)


# Credits
- [minijinja-cli](https://crates.io/crates/minijinja-cli) [github](https://github.com/mitsuhiko/minijinja/tree/main/minijinja-cli)
- [minijinja](https://docs.rs/minijinja/latest/minijinja/) [github](https://github.com/mitsuhiko/minijinja)
- [jinja](https://github.com/pallets/jinja/)

# Similar Tools
- [gomplate](https://docs.gomplate.ca/)
