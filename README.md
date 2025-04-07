# Deploy-Contract-Seismic-Devnet

This guide walks you through deploying a smart contract on **Seismic DevNet** using **Seismic Foundry**.

---

## ⚙️ Prerequisites

Before starting, make sure your system is up to date and has the necessary packages installed.

---

## 🧰 Installation Steps

Run the following commands in your terminal to install everything needed:

```bash
# System update & required tools
sudo apt update
sudo apt upgrade -y
sudo apt install -y curl git build-essential file unzip

# Install Rust
curl https://sh.rustup.rs -sSf | sh
source "$HOME/.cargo/env"
rustc --version

# Install jq
sudo apt install -y jq
jq --version

# Install Seismic Foundry
curl -L -H "Accept: application/vnd.github.v3.raw" "https://api.github.com/repos/SeismicSystems/seismic-foundry/contents/sfoundryup/install?ref=seismic" | bash
source ~/.bashrc
sfoundryup
```

⏳ **Wait 5–30 minutes** until you see:

```
sfoundryup: Seismic Foundry installation complete.
```

That means installation was successful ✅

---

## 📦 Clone and Deploy the Contract

After Foundry is installed, clone the repository and deploy the contract:

```bash
git clone --recurse-submodules https://github.com/SeismicSystems/try-devnet.git
cd try-devnet/packages/contract/
bash script/deploy.sh
```

---

## 🌐 Add Seismic DevNet to Your Wallet

Manually add the Seismic DevNet test network in MetaMask (or other wallets):

- **Network Name:** Seismic Devnet  
- **RPC URL:** https://node-2.seismicdev.net/rpc  
- **Chain ID:** 5124  
- **Currency Symbol:** ETH  
- **Block Explorer:** https://explorer-2.seismicdev.net/

---

## 🪙 Fund the Deployment Wallet

After running the deploy script, you’ll see a **new wallet address** printed in the terminal. You need to send test ETH to this address.

Steps:

1. Visit the faucet: [https://faucet-2.seismicdev.net/](https://faucet-2.seismicdev.net/)
2. Request some test ETH to your main wallet.
3. From your main wallet, send **0.05 ETH** to the wallet address generated during deploy.
4. Wait **2–3 minutes**, then press **Enter** in the terminal to continue.

If successful — the contract is deployed 🥳

---

## ✅ Done!

Your contract is now deployed to **Seismic DevNet**. You’ve installed the toolchain, added the network, and tested funding & deployment. Well done!

Happy hacking 👨‍💻🚀
