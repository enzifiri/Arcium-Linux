# Arcium-Ubuntu

```
sudo apt-get update && sudo apt-get upgrade -y
apt install curl iptables build-essential git wget jq make gcc nano tmux htop nvme-cli pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev screen -y
```

# Rust + Cargo Setup
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
rustc --version
cargo --version
```

# Solana CLI
```
sh -c "$(curl -sSfL https://release.anza.xyz/stable/install)"
export PATH="/Users/test/.local/share/solana/install/active_release/bin:$PATH"
```
# Yarn 
```
curl -sSL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update -y
sudo apt-get install yarn -y
```
# Anchor 
```
cargo install --git https://github.com/coral-xyz/anchor avm --force
avm install latest
avm use latest
echo 'export PATH="/root/.avm/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
anchor --version
```
# Docker + Docker-Compose
```
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
sudo docker run hello-world
```

# Arcium CLI

arcup is the version manager used to manage Arcium tools (including CLI and MPC node binaries). Follow these steps for installation:

1. Download arcup
Replace <YOUR_TARGET> with your platform (aarch64_linux, x86_64_linux, aarch64_macos, x86_64_macos) and run the following command:
```
TARGET=<YOUR_TARGET> && curl -u testnet_user_20842437:ZTi9igBU6icam0y2 "https://bin.arcium.com/download/arcup_${TARGET}_0.1.30" -o ~/.cargo/bin/arcup && chmod +x ~/.cargo/bin/arcup

arcup install
arcium --version
```

