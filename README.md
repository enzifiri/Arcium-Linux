# Arcium Ubuntu Setup

```
sudo apt-get update && sudo apt-get upgrade && sudo apt-get install -y pkg-config build-essential libudev-dev libssl-dev
apt install curl iptables build-essential git wget jq make gcc nano tmux htop nvme-cli pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev screen -y
```
<details>
  <summary> <h2> Rust + Cargo Setup </summary> </h2>
    
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
rustc --version
cargo --version
```
</details>
<details>
  <summary> <h2> Solana CLI Setup </summary> </h2>

```
sh -c "$(curl -sSfL https://release.anza.xyz/stable/install)"
export PATH="/Users/test/.local/share/solana/install/active_release/bin:$PATH"
```
</details>
<details>
  <summary> <h2> Yarn Setup </summary> </h2>

```
curl -sSL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update -y
sudo apt-get install yarn -y
```
</details>
<details>
  <summary> <h2> Anchor Setup </summary> </h2>

```
cargo install --git https://github.com/coral-xyz/anchor avm --force
avm install latest
avm use latest
echo 'export PATH="/root/.avm/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
anchor --version
```
</details>

<details>
  <summary> <h2> Docker + Docker-Compose </summary> </h2>

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
</details>


# Arcium CLI

arcup is the version manager used to manage Arcium tools (including CLI and MPC node binaries). Follow these steps for installation:

1. Download arcup
Replace <YOUR_TARGET> with your platform (aarch64_linux, x86_64_linux, aarch64_macos, x86_64_macos) and run the following command:
```
TARGET=<YOUR_TARGET> && curl -u testnet_user_20842437:ZTi9igBU6icam0y2 "https://bin.arcium.com/download/arcup_${TARGET}_0.1.30" -o ~/.cargo/bin/arcup && chmod +x ~/.cargo/bin/arcup

arcup install
arcium --version
```
Done, lets start build!

![image](https://github.com/user-attachments/assets/707b167f-ab1f-4289-ba81-4c0b6d08811b)

# Docs
https://arcium.gitbook.io/arcium-docs-testnet/TVGjj38fvTGJzu2su5ut
