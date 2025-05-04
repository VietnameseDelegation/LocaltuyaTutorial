# Vytvoření virtuálního stroje

Nahraj appliance image do svého hypervizoru virtuálního stroje.

> **Note:** Můžeš virtuálnímu stroji přidělit libovolné množství prostředků – doporučuje se ale dostatek podle toho, jaké add-ony plánuješ používat.

### Minimální doporučené prostředky:
- 2 GB RAM  
- 32 GB Storage  
- 2 vCPU  

### Postup:
1. Vytvoř nový virtuální stroj.
2. Vyber typ **Linux** a verzi **Linux 2.6 / 3.x / 4.x (64-bit)**.
3. V sekci **Hardware** nastav paměť a počet CPU.  
   - Zaškrtni **Enable EFI** – pokud nebude EFI zapnuté, HAOS nenabootuje.
4. V části **Hard Disk** vyber **Use an existing virtual hard disk file**  
   - Zvol `.vdi` soubor stažený z:  
     [https://www.home-assistant.io/installation/windows](https://www.home-assistant.io/installation/windows)
5. Jdi do **Network > Adapter 1**  
   - Zvol **Bridged Adapter** a vyber svůj síťový adaptér.  
   > **Poznámka:** Bridged adapter funguje pouze při připojení přes Ethernet. Wi-Fi není podporována.
6. Spusť virtuální stroj.  
   - Po nabootování se připoj přes:  
     - `http://homeassistant.local:8123/`  
     - `http://homeassistant:8123/`

---

# Stahování doplňkového tržiště HACS

- Stránka HACS:  
  [https://hacs.xyz/docs/use/download/download/#to-download-hacs](https://hacs.xyz/docs/use/download/download/#to-download-hacs)

- Přímý odkaz pro přidání do Home Assistant:  
  [https://my.home-assistant.io/redirect/supervisor_addon/?addon=cb646a50_get&repository_url=https%3A%2F%2Fgithub.com%2Fhacs%2Faddons](https://my.home-assistant.io/redirect/supervisor_addon/?addon=cb646a50_get&repository_url=https%3A%2F%2Fgithub.com%2Fhacs%2Faddons)

### Postup:
1. Klikni na výše uvedený odkaz pro přidání repozitáře do Home Assistant.
   - Potvrď URL a klikni **Open link**
   - V dialogovém okně **Missing add-on repository** klikni na **Add**
2. V části **Get HACS add-on** klikni na **Install**
3. Klikni na **Start**
4. Otevři **Logs** doplňku a následuj instrukce
5. Restartuj Home Assistant
6. Jdi do **Settings > Devices & services**
7. Vymaž cache prohlížeče  
   > HACS se nezobrazí bez tvrdého obnovení nebo smazání cache
8. Vpravo dole klikni na **+ Add integration**
9. Najdi a zvol **HACS**

---

# Stažení a nastavení LocalTuya

Repozitář na GitHubu:  
[https://github.com/rospogrigio/localtuya](https://github.com/rospogrigio/localtuya)

> Stáhni LocalTuya a restartuj Home Assistant, než budeš pokračovat.

### Postup:
1. Stáhni si aplikaci **Tuya Smart** do mobilu  
   - Připoj chytré zařízení přes tuto aplikaci k Wi-Fi síti, kterou chceš použít
2. Vytvoř účet na:  
   [https://platform.tuya.com/](https://platform.tuya.com/)  
   - Vytvoř nový **cloud project**
3. V přehledu projektu najdi **Client ID** a **Client Secret** – poznamenej si je
4. Jdi do sekce **Devices > Link app account**
5. Klikni na **Add app account**
6. Otevři aplikaci Tuya Smart, klikni na **Me**, pak vpravo nahoře na ikonu QR
7. Naskenuj QR kód z platform.tuya.com
8. Zapiš si **Device ID**
9. Potvrď a zapiš si **User ID**
10. Otevři dashboard Home Assistant
11. Jdi do **Settings > Devices & services**
12. Znovu smaž cache prohlížeče
13. Klikni na **+ Add integration**
14. Najdi a klikni na **LocalTuya**
15. Vyplň **app config** (Client ID, Secret, User ID, Device ID)
16. Klikni na **Configure** a zvol **add a new device**
17. Vyplň formulář – hlavní je správný **Device ID**, ostatní není tak důležité
18. Hotovo!
