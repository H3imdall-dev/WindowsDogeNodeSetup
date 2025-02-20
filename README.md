![Windows Doge Node Setup](https://github.com/user-attachments/assets/e3e4ee4e-dcfc-448f-bb14-dabb90215b80)

# **Dogecoin Node Setup on Windows 🚀**
*A step-by-step guide to setting up a Dogecoin node on a Windows machine.*

---

## **🌐 Router Configuration (Port Forwarding & Static IP)**
To allow your Dogecoin node to communicate properly with the network, follow these steps:

### **Step 1: Log into Your Router**
1. Open a web browser and go to:
   ```
   192.168.0.1
   ```
2. Log in to your router (default credentials are usually on a label on the router).

### **Step 2: Assign a Static IP**
1. Navigate to **DHCP Settings**.
2. Locate your machine in the connected devices list.
3. Assign it a **static IP address**, e.g.:
   ```
   eg 192.168.0.24 make your own
   ```
4. **Remember this IP**, as you will need it later.

### **Step 3: Open Port 22556**
1. Go to **Port Forwarding** settings.
2. Create a new rule:
   - **Internal IP:** *(Your static IP from Step 2)*
   - **Port:** `22555` (start) 22556(end)
   - **Protocol:** **Both (TCP & UDP)**
   - **Enable the rule**

✅ **Done!** Your router is now configured for Dogecoin node communication.

---

## **🛠️ System Requirements**
- **Minimum Specs:**
  - 4 CPU Cores
  - 220+ GB Storage
  - Windows 10/11 (64-bit)

---

## **🛠️ Option 1: Installing via Windows Installer**
1. Go to the official **Dogecoin Core** release page:  
   📥 **[Dogecoin Core Releases](https://github.com/dogecoin/dogecoin/releases/latest)**
2. Download the latest Windows **installer** (`dogecoin-<version>-win64-setup.exe`).
3. Run the installer and follow the setup prompts.
4. Choose the installation directory (default is recommended).
5. Once installed, open **Dogecoin Core** from the Start Menu.
6. Allow the node to **run for 1 minute** to initialize the necessary files.
7. Close Dogecoin Core completely.
8. Navigate to: (the app data folder is usally hidden you can show hidden folders to show it or just paste the code below in the bar at the top of the file explorer just change it to your username..
   ```
   C:\Users\YourUsername\AppData\Roaming\Dogecoin\    
   ```
9. Right-click inside the folder and create a new text file named:
   ```
   dogecoin.conf
   ```
10. Open `dogecoin.conf` with **Notepad** (or a text editor) and paste the following:
    ```
    rpcuser=your_username
    rpcpassword=your_password
    rpcallowip=127.0.0.1
    maxconnections=50
    rpcport=22555
    server=1
    ```
11. **Save and close** the file.
12. Reopen **Dogecoin Core** and allow it to sync completely (this may take several hours).
13. **Done!** Your node is now running.

---

## **🛠️ Option 2: Installing via Command Line**
### **Step 1: Download & Extract Dogecoin Core**
1. Go to the official **Dogecoin Core** release page:  
   📥 **[Dogecoin Core Releases](https://github.com/dogecoin/dogecoin/releases/latest)**
2. Download the latest Windows release (`dogecoin-<version>-win64.zip`).
3. Extract the downloaded ZIP file to a **permanent folder**, e.g.,
   ```
   C:\DogecoinCore\
   ```

### **Step 2: Start Dogecoin Core for Initialization**
1. Open **File Explorer** and navigate to:
   ```
   C:\DogecoinCore\bin\
   ```
2. Double-click **`dogecoind.exe`** to start the Dogecoin node.
3. **Allow firewall access** when prompted.
4. Let it **run for 1 minute**, then close it (**Ctrl + C** if running in a command prompt).

### **Step 3: Configure Dogecoin Core**
1. Open **File Explorer** and navigate to:
   ```
   C:\Users\YourUsername\AppData\Roaming\Dogecoin\
   ```
2. Right-click inside the folder and create a new text file named:
   ```
   dogecoin.conf
   ```
3. Open `dogecoin.conf` with **Notepad** (or a text editor) and paste the following:
   ```ini
   rpcuser=your_username
   rpcpassword=your_password
   rpcallowip=127.0.0.1
   maxconnections=50
   rpcport=22555
   server=1
   ```
4. **Save and close** the file.
5. Reopen **Dogecoin Core** and allow it to sync completely (this may take several hours).

### **Step 4: Verify Node Status**
Open **Command Prompt (cmd.exe)** and run:
```powershell
cd C:\DogecoinCore\bin\
dogecoin-cli getblockcount
```
- This will show the **current block count** and indicate syncing progress.

To check active connections:
```powershell
dogecoin-cli getconnectioncount
```
- If **connections = 8**, your **port forwarding may be incorrect**.

---

## **🛠️ Step 5: Set Dogecoin Core to Run on Startup**
To ensure your node runs automatically:
1. Open **Task Scheduler** (`Win + S`, search "Task Scheduler").
2. Click **Create Basic Task** → Name it "Dogecoin Node".
3. Choose **"When the computer starts"**.
4. Click **Next**, then "Start a Program".
5. Browse to **`dogecoind.exe`** and select it.
6. Click **Finish**.

✅ **Your node will now start automatically!**

---

## **🚀 Summary**
### **✔️ What We Did:**
- Configured **Router Port Forwarding & Static IP**
- Downloaded & Installed **Dogecoin Core**
- Configured **dogecoin.conf**
- Started the **Dogecoin Node**
- Verified **Sync & Connections**
- Set **Dogecoin Core to Run on Startup**

💚 **You now have a fully functional Dogecoin Node on Windows!** 🐶🚀  

---

## **🙋 Need Help?**
If you have any issues, feel free to **open an issue** or reach out to the **@Heimdall_bull**on X! 🐕✨  

---
🚀 **Happy Mining & Supporting the Dogecoin Network!** 🐶

