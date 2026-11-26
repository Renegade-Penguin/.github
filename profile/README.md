<div align="center">

# 🐧 Renegade Penguin

**The expanded project home for work by [ChiefGyk3D](https://github.com/ChiefGyk3D)**

Cybersecurity · Linux · Amateur radio · Homelab · Automation · Hardware

[renegadepenguinllc.com](https://renegadepenguinllc.com) for consulting · [chiefgyk3d.com](https://chiefgyk3d.com) for the blog and technical journal

[![Mastodon](https://img.shields.io/badge/-Mastodon-202020?style=for-the-badge&logo=mastodon&logoColor=FBB03B)](https://social.chiefgyk3d.com/@chiefgyk3d)
[![Bluesky](https://img.shields.io/badge/-Bluesky-202020?style=for-the-badge&logo=bluesky&logoColor=FBB03B)](https://bsky.app/profile/chiefgyk3d.com)
[![Matrix](https://img.shields.io/badge/-Matrix-202020?style=for-the-badge&logo=matrix&logoColor=FBB03B)](https://matrix.to/#/#renegade-penguin:chiefgyk3d.com)
[![Discord](https://img.shields.io/badge/-Discord-202020?style=for-the-badge&logo=discord&logoColor=FBB03B)](https://discord.chiefgyk3d.com)
[![YouTube](https://img.shields.io/badge/-YouTube-202020?style=for-the-badge&logo=youtube&logoColor=FBB03B)](https://youtube.com/@ChiefGyk3D)
[![Twitch](https://img.shields.io/badge/-Twitch-202020?style=for-the-badge&logo=twitch&logoColor=FBB03B)](https://twitch.tv/chiefgyk3d)
[![Kick](https://img.shields.io/badge/-Kick-202020?style=for-the-badge&logo=kickstarter&logoColor=FBB03B)](https://kick.com/chiefgyk3d)
[![TikTok](https://img.shields.io/badge/-TikTok-202020?style=for-the-badge&logo=tiktok&logoColor=FBB03B)](https://tiktok.com/@chiefgyk3d)
[![Instagram](https://img.shields.io/badge/-Instagram-202020?style=for-the-badge&logo=instagram&logoColor=FBB03B)](https://www.instagram.com/chiefgyk3d/)
[![Pixelfed](https://img.shields.io/badge/-Pixelfed-202020?style=for-the-badge&logo=pixelfed&logoColor=FBB03B)](https://pics.chiefgyk3d.com/ChiefGyk3D)

[![StreamElements](https://img.shields.io/badge/StreamElements-Tip-FBB03B?style=for-the-badge&labelColor=202020)](https://streamelements.com/chiefgyk3d/tip)
[![Patreon](https://img.shields.io/badge/Patreon-Support-FBB03B?style=for-the-badge&logo=patreon&logoColor=FBB03B&labelColor=202020)](https://patreon.com/chiefgyk3d)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-Support-FBB03B?style=for-the-badge&logo=ko-fi&logoColor=FBB03B&labelColor=202020)](https://ko-fi.com/chiefgyk3d)
[![Merch](https://img.shields.io/badge/Merch-shop.chiefgyk3d.com-FBB03B?style=for-the-badge&logo=shopify&logoColor=FBB03B&labelColor=202020)](https://shop.chiefgyk3d.com/)
[![Support page](https://img.shields.io/badge/Crypto%20%26%20Merch-support.chiefgyk3d.com-FBB03B?style=for-the-badge&logo=bitcoin&logoColor=FBB03B&labelColor=202020)](https://support.chiefgyk3d.com)

<sub>**Related profiles:** [ChiefGyk3D](https://github.com/ChiefGyk3D) is the personal account, home of the projects listed under "On the personal account" below. The blog is [chiefgyk3d.com](https://chiefgyk3d.com).</sub>

**🔗 All my links:** [links.chiefgyk3d.com](https://links.chiefgyk3d.com)

</div>

---

## <a name="why-this-exists"></a><img src="https://raw.githubusercontent.com/Renegade-Penguin/.github/main/profile/brand/bar.svg" height="22" alt=""> Why this exists

As my projects have grown in size, scope, and complexity, I needed to move beyond what made sense to keep entirely under a personal GitHub account. This organization gives larger projects, their related repositories, automation, documentation, and shared infrastructure a cleaner place to live: one project board across a family of repos, CI credentials scoped to an app instead of a person, and room for a second maintainer when one shows up.

That does **not** mean my personal GitHub is going away.

Work is actively shared between **<https://github.com/ChiefGyk3D>** and this organization. Depending on the project, you may find repositories here or under my personal account, and both are part of the same body of work, maintained by me. A project generally moves here when it outgrows a single repo or needs things a personal account cannot do well, and it keeps its history, issues, and links when it does. Renegade Penguin LLC is the entity behind the work; the code stays open source either way. The LLC takes cybersecurity and IT consulting, education, and speaking work through [renegadepenguinllc.com](https://renegadepenguinllc.com).

## <a name="what-lives-here"></a><img src="https://raw.githubusercontent.com/Renegade-Penguin/.github/main/profile/brand/bar.svg" height="22" alt=""> What lives here

### Sites and profiles

- The LLC site is [renegadepenguinllc.com](https://renegadepenguinllc.com), with its source at [Renegade-Penguin/renegade-penguin-site](https://github.com/Renegade-Penguin/renegade-penguin-site).
- The rest of the work lives on the [ChiefGyk3D personal GitHub profile](https://github.com/ChiefGyk3D).
- The blog and technical journal is [chiefgyk3d.com](https://chiefgyk3d.com).

### The Hammunition suite

<p align="center">
  <img src="https://raw.githubusercontent.com/Renegade-Penguin/Hammunition/main/docs/images/logo.png" alt="Hammunition" width="300">
</p>

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

### On the personal account

These stay under [ChiefGyk3D](https://github.com/ChiefGyk3D). The full grouped list is in its [open-source projects section](https://github.com/ChiefGyk3D#-open-source-projects).

- **[Clouds Against Humanity](https://github.com/ChiefGyk3D/Clouds-Against-Humanity):** a small, locked-down DigitalOcean environment for learning cloud security, zero trust, and infrastructure as code.
- **[Reach Around](https://github.com/ChiefGyk3D/Reach-Around):** self-hosted creator analytics, link page, and media kit.
- **[Stream Daemon](https://github.com/ChiefGyk3D/Stream-Daemon):** announces your go-live and sign-off to Mastodon, Bluesky, Discord, and Matrix.
- **[git-your-ship-together](https://github.com/ChiefGyk3D/git-your-ship-together):** reusable, hardened GitHub Actions workflows.
- **[Mother Ticker](https://github.com/ChiefGyk3D/mother-ticker):** GPS-disciplined stratum-1 NTP appliances on Raspberry Pi 4.
- **[SolarStorm Scout](https://github.com/ChiefGyk3D/solarstorm_scout):** NOAA space-weather alerts for HF propagation and aurora.
- **[Typo Sniper](https://github.com/ChiefGyk3D/typo-sniper):** typosquatting and domain threat intelligence scanner.
- **[Department of Internal Arguments](https://github.com/ChiefGyk3D/department-of-internal-arguments):** shared AI agent personas and domain knowledge.
- Plus the SIEM stacks, FrankenLLM, the daemon family, and the Linux utilities.

## <a name="what-to-expect"></a><img src="https://raw.githubusercontent.com/Renegade-Penguin/.github/main/profile/brand/bar.svg" height="22" alt=""> What to expect

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

## <a name="support-the-work"></a><img src="https://raw.githubusercontent.com/Renegade-Penguin/.github/main/profile/brand/bar.svg" height="22" alt=""> Support the work

Everything here is open source and built on my own time and hardware. If something saved you a weekend, the ways to send a little back, all also on [support.chiefgyk3d.com](https://support.chiefgyk3d.com):

- [Patreon](https://patreon.com/chiefgyk3d) · [Ko-fi](https://ko-fi.com/chiefgyk3d) · [StreamElements tip](https://streamelements.com/chiefgyk3d/tip) · [Merch](https://shop.chiefgyk3d.com/)

| Currency | Address |
|---|---|
| Bitcoin (BTC) | `bc1qztdzcy2wyavj2tsuandu4p0tcklzttvdnzalla` |
| Monero (XMR) | `84Y34QubRwQYK2HNviezeH9r6aRcPvgWmKtDkN3EwiuVbp6sNLhm9ffRgs6BA9X1n9jY7wEN16ZEpiEngZbecXseUrW8SeQ` |
| Ethereum (ETH) | `0x554f18cfB684889c3A60219BDBE7b050C39335ED` |
| Solana (SOL) | `5T8h3HbyvHgLxwXgchRYbHSqRjZyAr8J7uwjLN9Fh8Jh` |

For additional projects, contributions, and ongoing development, also check out **<https://github.com/ChiefGyk3D>** and the blog and technical journal at **<https://chiefgyk3d.com>**.
