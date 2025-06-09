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

- **Pfsense:** Futtatok rajta **DHCP szervert**, **NTP szervert**, **Wireguardot**, **OpenVPN-t**, beállítottam rajta **DDNS-t**.
- **Publikus és privát domain névoldásának mechanizmusa:** Én a **Namecheap-en** regisztráltam saját domain-t, amit a **Cloudflare** nameserverre költöztettem. Publikusan nem tettem elérhetővé szolgáltatásokat. Az **Nginx Proxy Manager** segítségével a szolgáltatásaimat nevükön érem el, és nem kell IP címeket portszámokkal megjegyeznem. **SSL tanúsítványt** is szereztem az Nginix Proxy Manager-en futó Let's Encrypt szolgáltatással, ehhez jól jött a korábban regisztrált publikus domain, a **DNS 01 challanger + wildcard** megvalósításához. A privát domainem (otthoni.local) a **Bind9** DNS szerverem oldja fel, amit nem tud feloldani, a 8.8.8.8-ra forwardolja. **DNS override-ot** is alkalmazok annak érdekében, hogy ha a homelabommal egy hálózaton vagyok, akkor példáu a nextcloud.trkrolf.com kérést ne a publikus DNS szerverek oldják fel, hanem az én privát DNS szerverem. Ennek érdekében a *.trkrolf.com-ot a lokális DNS szerverem ip címére irányítom.
- **SSH biztonságossá tétele**: **Timeout** beállítása, jelszó helyett **SSH key** használata, lehetőség szerint **root user tiltása** SSH-n.
- **Monitorozás:** Zabbix Agent beállítása Linux és Windows gépre. Csináltam pár alap **problem triggerelést**, például 1 percig nem pingelhető egy gép, szabad tárhely egy szint alá csökken, CPU használtal egy érték fölő megy. Ugyanezeket riasztásban is megvalósítottam, **email értesítést** küldve. Saját **dashboard** létrehozása.
- **Rendszer backup:** A **Clonezillával** mentem el a Proxmox partíciót blokkszinten. Egy Proxmoxon virtualizált **Proxmox Backup Serverre** mentem a másik fizikai gépen futó VM és LXC példányokat.
- **Személyes fájlok backupja/szinkronizációja:**  **Nextcloud-ot** használok a fájlok megosztására a laptopommal. A fényképeimet a telefonomról egyirányú szinkronizációval mentem a homelabomra **FolderSync-el**, ugyanígy laptopomon erre a **FreeFileSync-et** használom. 
- **Ansible automation:** Használom CLI-ből és Semaphroe Web UI-ból egyaránt. Playbook segítségével VM és LXC frissítéseket automatizálom, közös usereket hozok létre, közös konfig fájlokat szerkesztek (pl.: NTP szerver megadása), időzóna beállítása. 
- **Reklámszűrés:** Pi-hole-t használok böngészéshez, hogy a reklálmokat DNS kérés szintjén szűrje, upstream szervere a BIND9 szerverem. 

---

## 🔮 Jövőbeli tervek (folyamatosan bővöl)

- **Nyitás Windows irányba** (Windows Server + Active Directory).
- **Monitorozás továbbfejlesztése** Grafana + Prometheus megismerése. Zabbix-al elkezdtem ismerkedni, de az Udemy videót félbehagytam, ezt befejezni.
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

