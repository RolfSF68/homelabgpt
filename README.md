# 🏡 Homelabom rövid áttekintése

## Bemutatkozás
Ez a projekt egy önállóan kialakított homelabot mutat be, amelynek célja az elméleti ismeretek valós környezetben történő kipróbálása, elmélyítése, új technológiák megismerése, miközben vállalati környezetet modellezek.
Ez a projekt egy önállóan kialakított homelabot mutat be, amelynek célja az elméleti ismeretek valós környezetben történő kipróbálása és elmélyítése, új technológiák megismerése, miközben valós vállalati környezetet modellezek.

> 🎯 **Célom**: fejleszteni szakmai kompetenciáimat és bemutatni, hogy IT rendszergazdai vagy DevOps gyakornoki pozícióban azonnal hozzá tudok járulni csapatodhoz.

---

## 🛠️ Alap technológiák és konfigurációk

| Terület              | Használt eszközök, projektek                       |
|----------------------|---------------------------------------------------|
| **Virtualizáció**     | Proxmox VE (2 gépes cluster), LXC, KVM VM-ek      |
| **Hálózat és tűzfal** | pfSense/OPNsense, VLAN-ok, DHCP, DNS (Bind9)      |
| **Webszolgáltatások** | Nginx Proxy Manager + Cloudflare DNS               |
| **Monitorozás**       | Zabbix – testreszabott host metric-ek, grafikonok|
| **Automatizálás**     | Ansible playbook-ok: telepítés, konfigurálás      |
| **Biztonság és mentés**| Fail2ban, Proxmox Backup Server, snapshot kezelések|
| **Tárhely, fájlkezelés** | Nextcloud LXC konténerrel                        |

---

## 🔍 Részletes projektpéldák

- **DNS szerver telepítése:** Bind9 használata belső hálózati névfeloldásra, automatizálva Ansible-lel.
- **Webproxy beállítása:** Nginx Proxy Manager konténerrel több aldomain kezelése, SSL automatizálás Cloudflare-rel.
- **Monitorozás:** Zabbix hostokhoz grafikonok, riasztások, host discovery, Ansible-lel frissítve.
- **Backup rendszer:** Proxmox mentések beállítása Proxmox Backup Server + snapshot stratégia, tesztelt restore-okkal.
- **Ansible automation:** infrastruktúra kiépítése és frissítése 10+ VM-en és LXC-n egyetlen playbookkal.

---

## 🖼️ Projekt képernyőképek (screenshots)

A projekt mappában található `screenshots/` könyvtárban elérhetőek képernyőképek, többek között:

- Zabbix dashboard hostokkal és riasztásokkal
- Ansible futtatások, telepítési lépések
- Proxmox interfész VM/LXC listával
- Nginx Proxy Manager és Cloudflare beállítások
- Nextcloud bejelentkezési és fájlkezelő felülete

---

## 🔮 Jövőbeli tervek

- Konténer-orchesztráció (Docker Swarm vagy Kubernetes tanulása, bevezetése)
- Enterprise hálózatépítés (Windows Server + Active Directory + Samba integráció)
- Jogosultság és naplózás fejlesztése (többrétegű jogosultságkezelés, tűzfal-logok feldolgozása)
- Webes monitoring dashboard fejlesztése (pl. Grafana alapú vizualizáció)

---

## 🌟 Mit mutatok meg ezzel a projekttel?

- Valós, komplex rendszert építettem fel – nem csak “Hello World”, hanem teljes IP-alapú belső hálózat, szolgáltatások és automatizált üzemeltetés.
- Profi GitHub struktúra, részletes dokumentáció, technológiai háttér és jövőbeli célkitűzések.
- Széleskörű technológiai tapasztalat: virtualizáció, hálózat, tárolás, automatizálás, monitorozás, biztonság.
- Proaktív tanulási attitűd, folyamatos fejlesztés.

---

## 🧭 Használat álláskereséshez

1. A GitHub profilodon vagy LinkedIn-en linkeld be a repót.
2. Interjún mutasd be a topológiát, az automatizálási és monitorozási megoldásokat.
3. Emeld ki, hogy az Ansible, Zabbix, Proxmox Backup Server hármasával hogyan oldod meg az üzemeltetési feladatokat.

---

## 📫 Kapcsolat

- GitHub: [github.com/RolfSF68/homelab](https://github.com/RolfSF68/homelab)  
- E-mail: *itt az e-mail címed*  
- LinkedIn: *itt a LinkedIn profilod linkje*

---

*Ez a projekt bizonyítéka annak, hogy komolyan veszem a szakmai fejlődést, és képes vagyok gyakorlati tudással támogatni egy IT csapatot.*

---

**Köszönöm, hogy megnézted!**

