# How to setup Node / Bridge in Hive OS for Spectre Network ($SPR)
Commands used in the video : [https://youtu.be/JxwO0n6OpAE](https://youtu.be/JxwO0n6OpAE)

## libc6 
```sh
echo "deb http://archive.ubuntu.com/ubuntu jammy main" >> /etc/apt/sources.list && apt update && apt upgrade -y && apt install g++-11 -y && apt install libc6 -y
```

## Setup node
```sh
mkdir spr_node && cd spr_node && wget https://github.com/spectre-project/rusty-spectre/releases/download/v0.3.14/rusty-spectre-v0.3.14-linux-gnu-amd64.zip && unzip rusty-spectre-v0.3.14-linux-gnu-amd64.zip && cd bin && screen -S node ./spectred --utxoindex --rpclisten=0.0.0.0:18110
```

### Ctrl+A+D (to detach the screen)

## Setup bridge
```sh
cd ../../ && mkdir spr_bridge && cd spr_bridge && wget https://github.com/spectre-project/spectre-stratum-bridge/releases/download/v0.3.15/spr_bridge-v0.3.15-linux-x86_64.zip && unzip spr_bridge-v0.3.15-linux-x86_64.zip && cd bin && screen -S bridge ./spr_bridge
```

### Ctrl+A+D (to detach the screen)

### Miner installation URL
```sh
https://github.com/BinaryExpr/spectre-miner/releases/download/v0.6.18/spectre_miner_x64-v0.6.18_linux.tar.gz
```

Start the miner

``sh
screen -ls`` (to see the active screens)

``sh
screen -r bridge`` (to attach the screen)

## Start the node
```sh
cd spr_node && cd bin && screen -S node ./spectred --utxoindex --rpclisten=0.0.0.0:18110
```

### Ctrl+A+D (to detach the screen)

## Start the bridge
```sh
cd ../../ && cd spr_bridge && cd bin && screen -S bridge ./spr_bridge
```
