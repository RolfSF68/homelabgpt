# 🏡 Homelabom rövid bemutatása

## Bemutatkozás
Ez a projekt egy önállóan kialakított homelabot mutat be, amelynek célja egy vállalati környezet modellezése.

> 🎯 **Célom**:
Az elméleti tudásom mellett gyakorlati tapasztalat szerzése, új technológiák kipróbálása és megismerése. A technológiák kiválasztásánál figyelembe vettem a jelenlegi munkaerőpiaci trendeket, de az erre rendelkezésemre álló büdzsét is.
Emellett fontos szempont volt, hogy az álláspályázatok során a munkáltatók könnyebben megismerhessék a tudásomat, hogy én vagyok-e a keresett személy, segítve így a kiválasztási folyamatot.

---

## 🛠️ Felhasznált technológiák általános áttekintése

| Terület              | Használt eszközök, projektek                       |
|----------------------|---------------------------------------------------|
| **OS** | CentOS 9 Stream, Ubuntu 22.04 desktop, Ubuntu 22.04 server, Windows 11, Windows Server 2019      |   
| **Virtualizáció**     | Proxmox VE (2 gépen), LXC, VM, Template + Cloud init  |
| **Tűzfal-router** | pfSense   |
| **DHCP** | ISC-KEA   |   
| **DNS** | DNS (Bind9) + Namecheap + Cloudflare|
| **VPN** | Tailscale, Wireguard, Openvpn|
| **Távoli elérés**     | SSH, RDP (Guacamole) |
| **Reverse proxy** | Nginx Proxy Manager               |
| **Monitorozás**       | Zabbix|
| **Automatizálás**     | Ansible+Semaphore, Cron+Cronicle       |
| **Biztonság és mentés**| Proxmox Backup Server, Clonezilla, Rclone, Nextcloud, FreeFileSync, Urbackup|
| **Reklámszűrés** | Pi-hole        |
| **APT cache proxy** | APT-Cache-NG        |
| **Dashboard** | Homarr        |
| **Radius, LDAP** | FreeRADIUS, FreeIPA |
| **Password management** | Vaultwarden        |
| **PXE boot** | iVentoy        |
| **IDS/IPS** | CrowdSec        |

---

## 🔍 Felhasznált technológiák részletesebb ismertetése

- **Saját publikus és privát domain:** Namecheap-en regisztráltam saját domain-t, amit utána a Cloudflare nameserverre költöztettem.
- **SSH biztonságossá tétele**: Legyen timeout, jelszó helyett SSH key használata, lehetőség szerint root user tiltása SSH-n.
- **Webproxy beállítása:** Nginx Proxy Manager konténerrel több aldomain kezelése, SSL automatizálás Cloudflare-rel.
- **Monitorozás:** Zabbix hostokhoz grafikonok, riasztások, host discovery, Ansible-lel frissítve.
- **Backup rendszer:** Proxmox mentések beállítása Proxmox Backup Server + snapshot stratégia, tesztelt restore-okkal.
- **Ansible automation:** infrastruktúra kiépítése és frissítése 10+ VM-en és LXC-n egyetlen playbookkal.

---

## 🔮 Jövőbeli tervek

- **Nyitás Windows irányba** (Windows Server + Active Directory).
- **Monitorozás továbbfejlesztése** (Grafana + Prometheus).
- **Cloud computing elmélyítése** (AWS, Azure).
- **Cloud storage** (Hetzned vagy Pcloud).
- **Ceph:** Három darab 2,5"-os SSD és egy Lenovo M920q Tiny PC beszerzése van tervben, amelyre Proxmoxot telepítek, hogy a meglévő gépeimmel együtt háromtagú klasztert alakíthassak ki. A célom, hogy a három SSD-t Ceph-be integráljam.
- **DIY PiKVM:**  KVM over IP hasznos lenne, ám az olcsóbb alternatívája, a PiKVM is igen költséges, ha készen veszi az ember, így én megamtól építeném meg. Venni szeretnék használtan RPI 4-et, amit megosztana a három gép között egy USB switch és HDMI switch. Az olcsóbb switch-ek csatornaváltása gombbal történik, én a gombot lecserélném egy ESP32-vel vezérelt tranzisztorra. Ehhez persze fontos, hogy a switch-ek könnyen szétszedhetőek legyenek, nagyobb roncsolás nélkül. Kicsit költségesebb, ha három RPI4-et veszek, minden géphez egyet, így nem kell USB switch és HDMI switch, és egyszerre mindhárom gép vezérelhető böngészőből, nem kell váltani köztük.
- **IDS/IPS továbbfejlesztése:** CrowdSec beállítása Nginx Proxy Managerre, és Suricata implementálása.
- **Biztonság és mentés bővítése:** Rsync, Rclone megismerése. Bareos és Kopia alkalmazása ezidáig sikeretelen volt, a klienseket nem tudom bevonni, ezt megoldani.
- **Ethernet autentikáció Radius szerverrel:** 802.1x port based autentikációt támogató switch vásárlása, és beállítani, hogy a Radius felügyeletet a portokon.
- **DNSSEC** 

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

