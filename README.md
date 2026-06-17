# 🦝 TRaSH Panda Guides: The Decoupled Media Ecosystem

> [!IMPORTANT]  
> **This repository contains the raw source code for the TRaSH Panda Guides DokuWiki.** > If you want to read the guide, view the diagrams, and copy the scripts, **[CLICK HERE TO READ THE LIVE WIKI](https://trashpanda.fisherflix.com)**.

Welcome to the **TRaSH Panda Guides**. While the legendary TRaSH Guides teach the community how to perfectly tune applications for media quality, the TRaSH Panda takes a step back to engineer the forest they live in. 

This repository contains a 37-page, enterprise-grade architecture blueprint for building a fully decoupled, multi-VLAN home media environment. 

## 🚨 The Problem It Solves
Most conventional home media deployments suffer from the **"Monolithic NAS Problem."** Running Plex, qBittorrent, and the ARR stack on a single operating system creates a massive single point of failure, networking conflicts, and severe security vulnerabilities. 

This architecture solves specific pain points for advanced homelab builders:
* **VLAN Isolation:** Safely separating the Plex Media Server (DMZ) from the ARR stack (Trusted LAN) using stateful firewall pinholes.
* **Storage Fabric:** Resolving NFS stale file handles and enforcing atomic hardlinks across distributed Linux compute nodes.
* **VPN Sandboxing:** Implementing absolute WireGuard (NordLynx) kill-switches so qBittorrent never leaks your true WAN IP.
* **Hardware Transcoding:** Offloading H.265 conversions via Unmanic to a dedicated bare-metal NVIDIA GPU, saving massive storage space without taxing your NAS processor.
* **Day-2 Operations:** Fully documented automated watchdogs and Veeam pre/post quiescence scripts for backing up live SQLite and .NET databases safely.

## 📂 Repository Structure
This blueprint is written in DokuWiki syntax (`.txt`). You can read the rendered, fully-interlinked documentation live at **[trashpanda.fisherflix.com](https://trashpanda.fisherflix.com)**.

* `/docs/architecture` - High-level topologies and deployment sequences.
* `/docs/network` - Switch ACLs and firewall rules.
* `/docs/compute` - Hypervisor and bare-metal OS tuning.
* `/docs/storage` - NAS arrays and NFS configurations.
* `/docs/services` - The ARR stack, VPNs, and Plex engine.
* `/docs/security` - NGINX reverse proxies and Certbot.
* `/docs/operations` - Maintenance, backups, and troubleshooting.
* `/docs/reference` - Centralized IP/Port matrices and bash scripts.

## 📝 Why DokuWiki Syntax (.txt)?
You might notice these files are `.txt` rather than standard Markdown (`.md`). This is a deliberate architectural choice. 

TRaSH Panda Guides are designed for the self-hosted community. By utilizing DokuWiki syntax:
1. **Zero Database Bloat:** The entire wiki is flat-file. There is no MySQL/MariaDB requirement to host this documentation.
2. **Instant Deployment:** You can clone this repository, drop the folders directly into your own local `/dokuwiki/data/pages/` directory, and have an instant, offline, fully-linked disaster recovery manual on your own secure LAN.
3. **Easy Backups:** Text files can be backed up via simple `rsync` cronjobs without requiring database dumps.

If you are just looking to read the guide, please visit the **[Live Web Version](https://trashpanda.fisherflix.com)**.

## 🤝 Contributing
Found a typo, have a better bash script, or want to add a new hardware topology? Pull Requests are highly encouraged! Please see `CONTRIBUTING.md` for guidelines.
