# 🏡 Homelabom rövid bemutatása

## Bemutatkozás
Ez a projekt egy önállóan kialakított homelabot mutat be, amelynek célja egy vállalati környezet modellezése.

> 🎯 **Célom**:
Az elméleti tudásom mellett gyakorlati tapasztalat szerzése, új technológiák kipróbálása és megismerése. A technológiák kiválasztásánál figyelembe vettem a jelenlegi munkaerőpiaci trendeket, de az erre rendelkezésemre álló büdzsét is.
Emellett fontos szempont volt, hogy az álláspályázatok során a munkáltatók könnyebben megismerhessék a tudásomat, hogy én vagyok-e a keresett személy, segítve így a kiválasztási folyamatot.

---

## 🛠️ Felhasznált technológiák

| Terület              | Használt eszközök, projektek                       |
|----------------------|---------------------------------------------------|
| **OS** | CentOS 9 Stream, Ubuntu 22.04 desktop, Ubuntu 22.04 server, Windows 11, Windows Server 2019      |   
| **Virtualizáció**     | Proxmox VE (2 gépen), LXC, VM-ek      |
| **Tűzfal-router** | pfSense   |
| **DHCP** | ISC-KEA   |   
| **DHCP** | DNS (Bind9)|
| **Távoli elérés**     | Tailscale, Wireguard, Openvpn, VNC, RDP, SSH, Guacamole |
| **Webszolgáltatások** | Nginx Proxy Manager, Cloudflare, Namecheap               |
| **Monitorozás**       | Zabbix|
| **Automatizálás**     | Ansible+Semaphore, Cron+Cronicle       |
| **Biztonság és mentés**| Proxmox Backup Server, Clonezilla, Rclone, Nextcloud|
| **Reklámszűrés** | Pi-hole        |
| **APT cache proxy** | APT-Cache-NG        |
| **Dashboard** | Homarr        |
| **Radius, LDAP** | FreeRADIUS, FreeIPA |
| **Password management** | Vaultwarden        |
| **PXE boot** | iVentoy        |
| **IDS/IPS** | CrowdSec        |

---

## 🔍 Részletes projektpéldák

- **DNS szerver telepítése:** Bind9 használata belső hálózati névfeloldásra, automatizálva Ansible-lel.
- **Webproxy beállítása:** Nginx Proxy Manager konténerrel több aldomain kezelése, SSL automatizálás Cloudflare-rel.
- **Monitorozás:** Zabbix hostokhoz grafikonok, riasztások, host discovery, Ansible-lel frissítve.
- **Backup rendszer:** Proxmox mentések beállítása Proxmox Backup Server + snapshot stratégia, tesztelt restore-okkal.
- **Ansible automation:** infrastruktúra kiépítése és frissítése 10+ VM-en és LXC-n egyetlen playbookkal.

---

## 🔮 Jövőbeli tervek

- Nyitás Windows irányba (Windows Server + Active Directory)
- Monitorozás továbbfejlesztése (Grafana + Prometheus)
- Cloud computing (AWS és Azure)

---

## 🖼️ Projekt képernyőképek (screenshots)

A projekt mappában található `screenshots/` könyvtárban elérhetőek képernyőképek, többek között:

- Zabbix dashboard hostokkal és riasztásokkal
- Ansible futtatások, telepítési lépések
- Proxmox interfész VM/LXC listával
- Nginx Proxy Manager és Cloudflare beállítások
- Nextcloud bejelentkezési és fájlkezelő felülete

---

**Köszönöm, hogy megnézted!**

