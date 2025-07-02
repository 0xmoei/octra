# Octra Public Testnet

![testnet](https://github.com/user-attachments/assets/aa4f05f1-0f0a-41d0-8ed8-df215b340c46)

## Join Discord
https://discord.gg/octra

---

## Requirements
Linux Ubuntu OS
* **VPS**: You can use a linux VPS to follow the guide
* **Windows**: Install Linux Ubuntu using WSL by following this [guide](https://github.com/0xmoei/Install-Linux-on-Windows)
* **Codespace**: If you don't have VPS or Windows WSL, you can use [Github Codespace](https://github.com/codespaces), create a blank template and run your codes.

---

## Install dependecies
Install & Update Packages:
```
sudo apt update && sudo apt upgrade -y
sudo apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y
```
Install Nodejs (Only VPS users)
```
sudo apt update
sudo curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs
node -v
npm install -g yarn
yarn -v
```

---

## Create wallet
### 1. Clone the repository
   ```bash
   git clone https://github.com/0xmoei/wallet-gen.git
   cd wallet-gen
   ```

### 2. Run the wallet generator webserver
   **Linux/macOS:**
   ```bash
   chmod +x ./start.sh
   ./start.sh
   ```


### 3. Open your browser
* **WSL/Linux/MAC users:**
  * Navigate to `http://localhost:8888` on browser

  
* **VPS users:**
  * 1- Open a new terminal
  * 2- Install **localtunnel**:
    ```
    npm install -g localtunnel
    ```
  * 3- Get a password:
    ```
    curl https://loca.lt/mytunnelpassword
    ```
  * The password is actually your VPS IP
  * 4- Get URL
    ```
    lt --port 8888
    ```
  * Visit the prompted url, and enter your password to access wallet generator page

### 4. Generate wallet
* Click "GENERATE NEW WALLET" and watch the real-time progress
* Save all the details of your Wallet

---

## Get Faucet
* Visit [Faucet page](https://faucet.octra.network/)
* Enter your address starting with `oct...` to get faucet

![image](https://github.com/user-attachments/assets/18597b40-eaad-434f-a026-cc4a56a6d1a8)

---
## Task 1: Send transactions

**1. Install Python**
```bash
sudo apt install python3 python3-pip python3-venv python3-dev -y
```

**2. Install CLI**
```bash
git clone https://github.com/octra-labs/octra_pre_client.git
cd octra_pre_client

python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

cp wallet.json.example wallet.json
```

**2. Add wallet to CLI**
```bash
nano wallet.json
```
* Replace following values:
  * `private-key-here`: Privatekey with `B64` format
  * `octxxxxxxxx...`: Octra address starting with `oct...`


**3. Start CLI**
```bash
python3 -m venv venv
source venv/bin/activate
python3 cli.py
```
* This should open a Testnet UI

![image](https://github.com/user-attachments/assets/0ba1d536-4048-4899-a977-4517b2e522cd)


**4. Send transactions**
* Send transactions to my address: `oct7vSMGG6SHz5p7Vz8mRmHqz3tFfb1A7CQristRap1unjk`
* Use [Octra Explorer](https://octrascan.io/) to find more octra addresses


**5. Use Alternative Script**
* If you have issue with official script, I just refined the script with optimizated UI, you can replace the current one with mine by executing this command:
```bash
curl -o cli.py https://raw.githubusercontent.com/0xmoei/octra/refs/heads/main/cli.py
```

**6. Share Feedback**

Always share your feedback about the week's task in discord

---

## Wait for next steps
Stay tuned.
