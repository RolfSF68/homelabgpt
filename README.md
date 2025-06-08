# Homelabom Proxmox alapon

Ez a homelab projekt azért jött létre, hogy gyakorlati úton mélyítsem rendszergazdai és hálózati ismereteimet. A folyamatos problémamegoldás lehetőséget ad új technológiák autodidakta elsajátítására és a tudásom elmélyítésére.

## Projekt céljai

### Megvalósított célok
- Gyakorlati rendszergazdai és hálózati tudás fejlesztése.
- Többféle operációs rendszer használata és ismerete:
  - *CentOS 9 Stream*
  - *Ubuntu 22.04* (desktop és server)
  - *Windows 11* és *Windows Server 2019*
- Virtualizációs tapasztalat megszerzése *Proxmox* környezetben, valamint korábbi ismeretek *XCP-ng* és *VMware* hypervisorokról.
- Több gép központi vezérlése *Ansible* és *Semaphore* segítségével.
- Távoli elérés biztosítása VPN, RDP és SSH megoldásokkal.
- Privát és publikus domain névkezelés megvalósítása:
  - Lokális DNS szerver *BIND9*-el
  - DNS override *Cloudflare* és *Pi-hole* segítségével
- Disaster recovery rendszerek bevezetése, mint például:
  - *Nextcloud*
  - *Clonezilla*
  - *Proxmox Backup Server*
- Egységes, központosított felhasználó- és jogosultságkezelés:
  - *FreeIPA*
  - *FreeRadius*

### Megvalósításra váró célok
- High Availability (HA) környezet kiépítése:
  - 3 node-os *Proxmox* cluster létrehozása
  - *Ceph* tároló 3x-os replikációval
- Hardver bővítés:
  - Lenovo M920Q beszerzése
  - További SSD-k vásárlása a tároláshoz és a clusterhez

---

## Módszertan és tanulási folyamat

Minden felmerülő problémát önállóan oldottam meg, angol nyelvű fórumok, cikkek, YouTube és Udemy videók segítségével. Törekedtem arra, hogy ne csak a hibák megoldását találjam meg, hanem az okokat is megértsem, ezáltal biztosítva, hogy a jövőben hasonló problémákkal hatékonyan tudjak szembenézni.

---

## Használt technológiák és eszközök

- Virtualizáció: *Proxmox VE*, *XCP-ng*, *VMware Workstation Pro*
- Operációs rendszerek: *CentOS 9 Stream*, *Ubuntu 22.04*, *Windows 11*, *Windows Server 2019*
- Automatizálás: *Ansible*, *Semaphore*
- Hálózat: VPN, *BIND9*, *Pi-hole*, *Cloudflare*
- Backup & Recovery: *Clonezilla*, *Proxmox Backup Server*
- Felhasználókezelés: *FreeIPA*, *FreeRadius*

---

Ha érdekelnek a részletes konfigurációk vagy kérdésed van, bátran keress meg!

---

