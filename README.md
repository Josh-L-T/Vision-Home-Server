# Vision | Debian Home Server

Vision is my bare-metal Debian homelab for practicing Linux administration,
networking, security, and service deployment. I manage it over SSH from
Ultron, my Lenovo Windows 11 Pro laptop. This is an ongoing portfolio
project for my Cyber Warrior Program.

## Hardware

| Component | Specification |
| --- | --- |
| CPU | Intel Core i7-7700K |
| Motherboard | ASUS ROG STRIX Z270E GAMING |
| Memory | 16 GB Corsair DDR4 |
| Storage | Samsung 990 EVO 1 TB NVMe |
| Cooling | NZXT Kraken X62 AIO |

## Current status

- Vision runs Debian on bare metal and connects over wired Ethernet.
- Ed25519 SSH access from Ultron was verified after a router change.
- The project log records root and password SSH login disabled.
- UFW and Fail2ban were active at the last recorded checks.
- Docker Engine and Compose are installed.
- Step 15B is in progress. The next Compose check uses a one-shot container
  with no published ports. The NGINX test is deferred pending security checks.

## Project files

- [Build notes and roadmap](docs/build-notes.md)
- [Deferred NGINX test plan](compose/nginx-test/README.md)
- [Optional NGINX Compose example](compose/nginx-test/compose.yaml)
