# HemiNetwork_Miner by @WwCfOfficial
---
- Offical Docs - [Hemi_Miner_CLI](https://docs.hemi.xyz/how-to-tutorials/tutorials/setup-part-1)
- Watch Video - [Youtube](https://youtu.be/M31JN1Q_sus?si=fC2FGce5jcSozm7q)

## 1. Binaries
- Visit [binaries](https://github.com/hemilabs/heminetwork/releases)
- Download (heminetwork_v0.11.5_linux_amd64.tar.gz) file
- Use Termius and copy the file to your VPS

- Now Follow commands
```bash
mkdir hemi-miner
```
```bash
cd hemi-miner
```
  
```bash
sudo apt update && sudo apt upgrade -y
```
```bash
sudo apt install screen
```
```bash
screen -S hemi
```
```bash
tar xvf heminetwork_v0.11.5_linux_amd64.tar.gz
```
```bash
cd heminetwork_v0.11.5_linux_amd64
```

## 2. Verify Configuration Success
- To ensure you downloaded the correct binaries and are able to run them, execute the command below:
```bash
./popmd --help
```
- This will display the help menu for popmd, indicating that it's installed and operational.

## 3. Generate Your Public Key
```bash
./keygen -secp256k1 -json -net="testnet" > ~/popm-address.json
```
```bash
cat ~/popm-address.json
```
- Result - Make sure to save everything

![image](https://github.com/user-attachments/assets/3138e88f-4553-4d0a-9b96-80538017a3fa)

1. Private key : EVM
2. pubkey_hash : btc address for faucet 

## 4. Fund your PoP Miner Address
- Find Your Wallet Address: Check the JSON from 3 for your pubkey_hash, which is your testnet Bitcoin address.
- Use discord to get faucet: [Hemi](https://discord.com/invite/hemixyz)

## 5. Set Variables
- In your console, execute the following commands while:
1. replacing <private_key> with the value found in the JSON from Step 5
2. replacing <fee_per_vB_integer> with the fee in sat/vB you want to pay (Normally 50)

```bash
export POPM_BTC_PRIVKEY=<private_key>
export POPM_STATIC_FEE=<fee_per_vB_integer>
export POPM_BFG_URL=wss://testnet.rpc.hemi.network/v1/ws/public
```
3. Check Current Fee Levels: Visit - [Mempool](https://mempool.space/testnet)
4. Look at the "sat/vB" numbers for the different transaction fee priorities. It is recommended to set the value to the "High Priority" value or slightly higher.
5. Re-run the command to set the POPM_STATIC_FEE environment variable from above each time you want to change the fee, and restart the PoP Miner afterwards.

## 6. Run the Miner
```bash
./popmd
```
- Output

![image](https://github.com/user-attachments/assets/172902fd-c9c6-4d7d-bc0f-e179ffd92c95)

## 7. Screen settings
- Once running use: CTRL A D (to detach from screen)
- To Check the screen again use :
```bash
screen -r hemi
```

---
- Check status : [Miner_Status](https://testnet.popstats.hemi.network/)

- Done !! Feel free to ask queries in telegram channel
- Telegram - https://t.me/WwCfAirdrops
- Youtube - https://youtube.com/@WwCfOfficial
- Twitter - https://x.com/WwCfOfficial