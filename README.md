Managing Software with APT, DNF, and Snap

Overview

This small slide deck (Marp) and README provide a presentation and demo plan for "Managing Software with APT, DNF, and Snap". The slides are in `slides/managing-software-aptdnf-snap.md`.

Environment

- Recommended: 2 VMs or containers
  - Debian/Ubuntu (example container image: ubuntu:24.04)
  - CentOS/RHEL/AlmaLinux (example container image: almalinux:9)
- You need sudo access in each environment.

Quick steps to run demo with containers

1. Debian/Ubuntu container (using docker/podman):

```bash
podman run -it --rm --name demo-ubuntu ubuntu:24.04 /bin/bash
# inside container
apt update
apt install -y cowsay snapd
# run commands from slides (see slides file for full list)
```

2. AlmaLinux container:

```bash
podman run -it --rm --name demo-alma almalinux:9 /bin/bash
# inside container
dnf makecache
dnf install -y cowsay
```

Notes about snap in containers: snaps often require systemd and additional setup; for simple demo, run snap on the host Ubuntu VM or skip snap and just show `snap find` output.

Export slides with Marp CLI

- Install Marp CLI (Node.js):

```bash
npm install -g @marp-team/marp-cli
```

- Export to PDF or HTML:

```bash
marp slides/managing-software-aptdnf-snap.md -o slides/managing-software-aptdnf-snap.pdf
marp slides/managing-software-aptdnf-snap.md -o slides/managing-software-aptdnf-snap.html
```

Presenter tips

- Run `apt update`/`dnf makecache` before installing during demo to avoid waiting long
- If network is slow, pre-pull container images and pre-install packages in snapshots

Files

- `slides/managing-software-aptdnf-snap.md` - Marp slide deck
- `README.md` - this file

Enjoy the demo!
