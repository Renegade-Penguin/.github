<div align="center">

# 🐧 Renegade Penguin

**The expanded project home for work by [ChiefGyk3D](https://github.com/ChiefGyk3D)**

Cybersecurity · Linux · Amateur radio · Homelab · Automation · Hardware

[![Mastodon](https://img.shields.io/badge/-Mastodon-6364FF?style=for-the-badge&logo=mastodon&logoColor=white)](https://social.chiefgyk3d.com/@chiefgyk3d)
[![Bluesky](https://img.shields.io/badge/-Bluesky-0285FF?style=for-the-badge&logo=bluesky&logoColor=white)](https://bsky.app/profile/chiefgyk3d.com)
[![Matrix](https://img.shields.io/badge/-Matrix-000000?style=for-the-badge&logo=matrix&logoColor=white)](https://matrix.to/#/#renegade-penguin:chiefgyk3d.com)
[![Discord](https://img.shields.io/badge/-Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.chiefgyk3d.com)
[![YouTube](https://img.shields.io/badge/-YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtube.com/@ChiefGyk3D)
[![Twitch](https://img.shields.io/badge/-Twitch-9146FF?style=for-the-badge&logo=twitch&logoColor=white)](https://twitch.tv/chiefgyk3d)
[![Kick](https://img.shields.io/badge/-Kick-53FC18?style=for-the-badge&logo=kickstarter&logoColor=black)](https://kick.com/chiefgyk3d)
[![TikTok](https://img.shields.io/badge/-TikTok-000000?style=for-the-badge&logo=tiktok&logoColor=white)](https://tiktok.com/@chiefgyk3d)
[![Instagram](https://img.shields.io/badge/-Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/chiefgyk3d/)
[![Pixelfed](https://img.shields.io/badge/-Pixelfed-FF6B2C?style=for-the-badge&logo=pixelfed&logoColor=white)](https://pics.chiefgyk3d.com/ChiefGyk3D)

[![StreamElements](https://img.shields.io/badge/StreamElements-Tip-blue?style=for-the-badge&logo=dollar-sign&logoColor=white)](https://streamelements.com/chiefgyk3d/tip)
[![Patreon](https://img.shields.io/badge/Patreon-Support-orange?style=for-the-badge&logo=patreon&logoColor=white)](https://patreon.com/chiefgyk3d)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-Buy%20Me%20a%20Coffee-ff5f5f?style=for-the-badge&logo=ko-fi&logoColor=white)](https://ko-fi.com/chiefgyk3d)
[![Merch](https://img.shields.io/badge/Merch-shop.chiefgyk3d.com-111111?style=for-the-badge&logo=shopify&logoColor=white)](https://shop.chiefgyk3d.com/)
[![Support page](https://img.shields.io/badge/Crypto%20%26%20Merch-support.chiefgyk3d.com-8B949E?style=for-the-badge&logo=bitcoin&logoColor=white)](https://support.chiefgyk3d.com)

**🔗 All my links:** [links.chiefgyk3d.com](https://links.chiefgyk3d.com)

</div>

---

## Why this exists

As my projects have grown in size, scope, and complexity, I needed to move beyond what made sense to keep entirely under a personal GitHub account. This organization gives larger projects, their related repositories, automation, documentation, and shared infrastructure a cleaner place to live: one project board across a family of repos, CI credentials scoped to an app instead of a person, and room for a second maintainer when one shows up.

That does **not** mean my personal GitHub is going away.

Work is actively shared between **<https://github.com/ChiefGyk3D>** and this organization. Depending on the project, you may find repositories here or under my personal account, and both are part of the same body of work, maintained by me. A project generally moves here when it outgrows a single repo or needs things a personal account cannot do well, and it keeps its history, issues, and links when it does. Renegade Penguin LLC is the entity behind the work; the code stays open source either way.

## What lives here

### 📡 The Hammunition suite

Hammunition turns a stock Debian-family install into an amateur radio and SDR workstation, then keeps it fed, controlled, and on time. One engine with its own console, and several small clients that only ever talk to it through its JSON interface.

```mermaid
flowchart LR
    subgraph engine["Hammunition"]
        direction TB
        console["hammunition console<br/>full-screen TUI"] --> cli["hammunition<br/>engine + YAML catalog"]
    end
    tray["Hammunition Devices<br/>Plasma / Qt tray applet"] --> engine
    bunker["Hammunition Bunker<br/>LAN mirror on your NAS"] --> engine
    engine --> tether["GPS tether<br/>gpsd to NMEA on loopback"]
    engine --> hill["Hammunition Hill<br/>operating-position dashboard"]
```

| Project | What it does |
|---|---|
| **[Hammunition](https://github.com/Renegade-Penguin/Hammunition)** | Turns an existing Debian-family install into a full amateur radio, SDR, and RF experimentation workstation. A declarative YAML catalog of software and hardware kept strictly separate from the Python engine that installs it: idempotent, `--dry-run` accurate, with a transaction log and honest per-distro capability reporting. Targets Parrot OS, Debian, Ubuntu, Kali, and Raspberry Pi OS. Ships its own full-screen terminal front end, `hammunition console`. |
| **[Hammunition Hill](https://github.com/Renegade-Penguin/hammunition-hill)** | Hammunition builds the shack computer; Hill is what you put on the monitor above it. Six dashboards and twenty-eight panels that run on your own machine, on your own network, and talk to nobody you did not name. Propagation, space weather, alerts, satellites, and callsign lookup. |
| **[Hammunition Devices](https://github.com/Renegade-Penguin/hammunition-tray)** | Plasma 6 system-tray applet (with a Qt tray for Xfce, LXQt, LXDE, MATE, and Cinnamon) for parking and waking the radio devices Hammunition has catalogued, switching GPS services, the machine's radios, and GPS time mode. Never touches sysfs, never runs as root, one polkit prompt per action. |
| **[Hammunition Bunker](https://github.com/Renegade-Penguin/hammunition-bunker)** | Keeps a verified copy of Hammunition's offline data (map regions, elevation tiles, reference files) on a NAS and serves it on your LAN, so a field laptop installs from the next room instead of the internet, checking every byte exactly as it would from the publisher. <sub>Early: tested against a fake engine, not yet on a real NAS.</sub> |
| **[Hammunition GPS tether](https://github.com/Renegade-Penguin/hammunition-gps-tether)** | Serves your GPS receiver's position from gpsd as NMEA on loopback only, for programs that can't talk to gpsd themselves. Standard library only, runs as you, never as root. |

More moves in as it outgrows the personal account. The reusable CI these repos call, [git-your-ship-together](https://github.com/ChiefGyk3D/git-your-ship-together), stays under the personal account because every repo of mine uses it.

## What to expect

My projects generally live somewhere around the intersection of:

- Cybersecurity and defensive engineering
- Linux and open source
- Amateur radio and emergency communications
- Homelab and infrastructure engineering
- Automation and DevOps
- AI and local LLM experimentation
- Hardware hacking and embedded systems
- Tools built because I had a problem and decided to solve it myself

A lot of what you see here starts as something I personally wanted or needed, then grows into something other people might find useful too. And expect experimentation, active development, weird ideas, practical tooling, and plenty of projects that cross the usual lines between software, infrastructure, cybersecurity, radio, and hardware.

## 🤝 Support the work

Everything here is open source and built on my own time and hardware. If something saved you a weekend, the ways to send a little back, all also on [support.chiefgyk3d.com](https://support.chiefgyk3d.com):

- [Patreon](https://patreon.com/chiefgyk3d) · [Ko-fi](https://ko-fi.com/chiefgyk3d) · [StreamElements tip](https://streamelements.com/chiefgyk3d/tip) · [Merch](https://shop.chiefgyk3d.com/)

| Currency | Address |
|---|---|
| Bitcoin (BTC) | `bc1qztdzcy2wyavj2tsuandu4p0tcklzttvdnzalla` |
| Monero (XMR) | `84Y34QubRwQYK2HNviezeH9r6aRcPvgWmKtDkN3EwiuVbp6sNLhm9ffRgs6BA9X1n9jY7wEN16ZEpiEngZbecXseUrW8SeQ` |
| Ethereum (ETH) | `0x554f18cfB684889c3A60219BDBE7b050C39335ED` |
| Solana (SOL) | `5T8h3HbyvHgLxwXgchRYbHSqRjZyAr8J7uwjLN9Fh8Jh` |

For additional projects, contributions, and ongoing development, also check out **<https://github.com/ChiefGyk3D>**.
