# Dark Horizon Network

DHN is a **TOR enabled**, Blockchain with a maximum PoW supply of **60,000 DHN**. By combining a **2MB Max Block Size** and **10 second target block time** with low transaction fees DHN offers everything you've been looking for in a quality Blockchain **<< now**.

## DNS Defence

In addition to using traditional DNS Seed Servers for peer discovery, DHN recognizes and addresses the risks, limitations and weaknesses of the traditional DNS system. By maintaining a presence on the Emercoin Distributed DNS Blockchain the Dark Horizon Network domain name records for:

* darkhorizonnetwork.coin
* darkhorizon.coin

are completely decentralized, uncensorable and cannot be altered, revoked or suspended by any authority. This approach offers the DHN user an additional layer of network security and accessibility by being able to locate active DHN nodes without being reliant on legacy DNS architecture.

## Value Relativity

Whatever value means to you, however you decide to measure it, consider that... In terms of coin circulation, the maximum PoW supply of 60,000 makes DHN **350x** more scarce than Bitcoin which has a maximum supply of 21,000,000 BTC.
On measures of service, Bitcoin has a hardcoded block time of 10 minutes whereas the hardcoded block time for DHN is 10 Seconds.

## Transparency

Full source code code for the DHN is available on github and community engagement and support is always welcome.


## Network Specifications

|Metric | Value |
|----|----|
| Symbol |  DHN |
|Maximum PoW Supply |	60,000 |
|Maximum Block Size |	2MB |
| PoW Maturity |	10 Blocks |
| Transaction Confirmations |	5 |
| Target Block Time |	10 Seconds |
| Dust Soft limit |	0.0001 DHN |
| Dust Hard limit |	0.0000001 DHN |
| Min Transaction Fee |	0.00001 DHN |
| Min Relay Transaction Fee |	0.00001 DHN |
| P2P Port |	5550 |
| RPC Port |	5555 |
| Algorithm |	Scrypt |


## PoW Block Reward Schedule

| Block-Start |	Block-End |	Block Reward |
|----|----|----|
|1 |	1 |	60^ |
|2 |	602 |	0.1 |
|603 |	54603 |	0.01 |
|54604 |	59394604 |	0.001|

^ 60 DHN have been allocated as Developer's Commission. This amount represents 0.1% of total 60,000 PoW supply. 

## Build Instructions - Ubuntu 16.04

```
cd ~/

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

sudo apt-get install git build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils libboost-all-dev software-properties-common libdb4.8-dev libdb4.8++-dev libminiupnpc-dev libzmq3-dev libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler libqt4-dev pwgen

git clone https://github.com/darkhorizonnetwork/darkhorizon.git

cd ~/darkhorizon/src/

make -f makefile.unix

// The core system has been made at this point (darkhorizond) -- continue to build the Wallet GUI

cd ~/darkhorizon

qmake

make

// The Wallet GUI is built at this point, need to create a ~/.darkhorizon/darkhorizon.conf before launching it:

mkdir ~/.darkhorizon && touch ~/.darkhorizon/darkhorizon.conf
RPCPASS="$(pwgen -s 37 1)"
cat <<EOF > ~/.darkhorizon/darkhorizon.conf
rpcuser=darkhorizonrpc
rpcpassword=$RPCPASS
EOF

// Launch Wallet GUI
~/darkhorizon/darkhorizon-qt

// Optional: clean up pwgen, we don't need it anymore.
sudo apt remove pwgen
```
