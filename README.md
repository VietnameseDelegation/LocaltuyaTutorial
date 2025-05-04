# Creating the Virtual Machine

Load the appliance image into your virtual machine hypervisor.

> **Note:** You are free to assign as many resources as you wish to the VM. Please assign enough based on your add-on needs.

### Minimum Recommended Assignments:
- 2 GB RAM  
- 32 GB Storage  
- 2 vCPU  

### Steps:
1. Create a new virtual machine.
2. Select type **Linux** and version **Linux 2.6 / 3.x / 4.x (64-bit)**.
3. Under **Hardware**, select the amount of memory and number of CPUs.  
   - Enable **EFI**. Home Assistant OS will not boot without EFI enabled.
4. Under **Hard Disk**, select **Use an existing virtual hard disk file**.  
   - Select the unzipped VDI file downloaded from:  
     [https://www.home-assistant.io/installation/windows](https://www.home-assistant.io/installation/windows)
5. Go to **Network > Adapter 1**:
   - Choose **Bridged Adapter** and select your network adapter.  
   > **Note:** Bridged Adapter only functions over a hardwired Ethernet connection. Wi-Fi is unsupported.
6. Start the virtual machine.  
   - Once fully booted, connect via:  
     - `http://homeassistant.local:8123/`  
     - `http://homeassistant:8123/`

---

# Downloading Custom Marketplace: HACS

- HACS Download Page:  
  [https://hacs.xyz/docs/use/download/download/#to-download-hacs](https://hacs.xyz/docs/use/download/download/#to-download-hacs)

- HACS Add-on Installation Link:  
  [https://my.home-assistant.io/redirect/supervisor_addon/?addon=cb646a50_get&repository_url=https%3A%2F%2Fgithub.com%2Fhacs%2Faddons](https://my.home-assistant.io/redirect/supervisor_addon/?addon=cb646a50_get&repository_url=https%3A%2F%2Fgithub.com%2Fhacs%2Faddons)

### Steps:
1. Click the add-on repository link above.
   - Confirm the URL is correct and select **Open link**.
   - In the "Missing add-on repository" dialog, select **Add**.
2. In "Get HACS add-on", select **Install**.
3. Start the add-on.
4. Navigate to the **add-on logs** and follow the instructions provided.
5. **Restart** Home Assistant.
6. Go to **Settings > Devices & services**.
7. **Clear your browser cache**.
   > HACS won’t show up in the list unless you clear your browser cache or do a hard refresh.
8. In the bottom right corner, select **+ Add integration**.
9. Search for **HACS** and select it.
10. **Authenticate** the integration.

---

# Setting Up LocalTuya

- LocalTuya GitHub Repository:  
  [https://github.com/rospogrigio/localtuya](https://github.com/rospogrigio/localtuya)

> Download LocalTuya and restart the device before proceeding.

### Steps:
1. Download the **Tuya Smart** app on your mobile device.
   - Connect your smart device through this app to the network you want it to operate on.
2. Create an account on:  
   [https://platform.tuya.com/](https://platform.tuya.com/)  
   - Create a new **Cloud Project**.
3. In the project **overview**, note your **Client ID** and **Secret**.
4. In the same menu, go to **Devices > Link App Account**.
5. Click **Add App Account**.
6. On your phone in **Tuya Smart**, go to **Me**.
   - Tap the rectangle icon in the top right corner.
7. **Scan the QR code** shown on the Tuya developer site.
8. Write down the **Device ID**.
9. After confirmation, write down the **User ID**.
10. Go to the **Home Assistant dashboard**.
11. In Home Assistant, go to **Settings > Devices & services**.
12. **Clear your browser cache**.
13. In the bottom right corner, select **+ Add integration**.
14. Search for and select **LocalTuya**.
15. Fill in the app config using your credentials (Client ID, Secret, User ID, Device ID).
16. Go to configure and select **Add a new device**.
17. Fill in the form (only the **Device ID** is important).
18. **You're done!**
