# Aleo-Testnet-Beta-Guide
Prior testnets have shown that while consumer-grade hardware can technically participate as a prover, it is unlikely to be effective due to high level of competition.
Minimum 1000 credit required to be eligible.


In this guide, i am using Contabo 17$ vps  ---    https://contabo.com/en/vps/ 
<img width="863" alt="image" src="https://github.com/Ramakotireddypammi/Aleo-Testnet-Beta-Guide/assets/136354890/482f20db-411b-495f-a784-869940859c62">





------------------
# Requirement  
## Aleo Prover that is competitive, the machine will need more than these requirements.
<img width="427" alt="image" src="https://github.com/Ramakotireddypammi/Aleo-Testnet-Beta-Guide/assets/136354890/1302d433-1232-4a9b-8aa4-fbb8deb618c8">







## Updating System 
```
sudo apt update && sudo apt update -y
```
<img width="806" alt="image" src="https://github.com/Ramakotireddypammi/Aleo-Testnet-Beta-Guide/assets/136354890/4e4d71ba-db30-495a-bae3-39c769de229e">


### Install GIT
Reply with ```y``` and continue 
```
sudo apt install git
```

### Install Build tool
```
sudo apt install -y build-essential clang libc6-dev libcurl4 libssl-dev
```
### Install Screen
```
sudo apt install screen -y
```

## Install Rust 
Reply with ```y``` and continue 
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

```

### Set Environment PATH
```
. "$HOME/.cargo/env"
source ~/.bashrc   
```

### Update RUST & Check version 
```
rustup update
rustc --version
```
<img width="799" alt="image" src="https://github.com/Ramakotireddypammi/Aleo-Testnet-Beta-Guide/assets/136354890/963b0a23-6c69-42b0-a17a-4c2293c1ce72">




## Clone SnarkOS Repository 
```
git clone --branch mainnet --single-branch https://github.com/AleoNet/snarkOS.git
cd snarkOS
git checkout tags/testnet-beta
```

<img width="748" alt="image" src="https://github.com/Ramakotireddypammi/Aleo-Testnet-Beta-Guide/assets/136354890/73eb32c1-d6e9-461e-b14a-7d0ce60ca1c2">



## Install dependencies 
```
./build_ubuntu.sh
```
<img width="751" alt="image" src="https://github.com/Ramakotireddypammi/Aleo-Testnet-Beta-Guide/assets/136354890/754b36a0-f628-46ea-82f9-b3064ffda2e7">

<img width="653" alt="image" src="https://github.com/Ramakotireddypammi/Aleo-Testnet-Beta-Guide/assets/136354890/6c6e8c61-b5b1-4586-9bdd-e9c4dad4677b">


## Install SnarkOS 
```
cargo install --locked --path .
```
<img width="804" alt="image" src="https://github.com/Ramakotireddypammi/Aleo-Testnet-Beta-Guide/assets/136354890/cc5f6042-30a2-4e3d-afb0-7fc686619d38">




## Open required port 

```
sudo ufw allow 4130/tcp
sudo ufw allow 3030/tcp
sudo ufw allow ssh
sudo ufw enable -y
sudo ufw status
```
<img width="613" alt="image" src="https://github.com/Ramakotireddypammi/Aleo-Testnet-Beta-Guide/assets/136354890/ed76b5fa-52b1-4301-9c9a-71fcbca07c03">



## Run ALEO Prover 

## Generate ALEO Account
### Save account details 
```
snarkos account new 
```


### Open Screen 
```
screen -S client
```




## Run Prover 
### Paste private key previously copied 
```
cd $HOME && cd snarkOS
./run-prover.sh --network 1
```
<img width="509" alt="image" src="https://github.com/Ramakotireddypammi/Aleo-Testnet-Beta-Guide/assets/136354890/2197f116-8647-41c3-b3a9-00a3b8d1c483">




DONE!!!





















