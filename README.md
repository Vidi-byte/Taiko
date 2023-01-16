# Taiko
## 1.  Smart contract 
### Install the latest release by using "foundryup".This is the easiest option for Linux and macOS users.
```
curl -L https://foundry.paradigm.xyz | bash
```
### let's start the bash
```
source /root/.bashrc
```
### This will download foundryup. Then install Foundry by running:
```
foundryup
```
#### If foundryup did not start, then try just restarting the terminal 
### Create a project with Foundry, and cd into it
```
forge init hello_foundry && cd hello_foundry
```
### Deploy the contract from your project, located at src/Counter.sol. Replace <YOUR_PRIVATE_KEY> with your private key, mentioned in the previous prerequisites section.
```
forge create --legacy --rpc-url https://l2rpc.a1.taiko.xyz --private-key <YOUR_PRIVATE_KEY> src/Counter.sol:Counter
```
#### Take the private key from your metamask that you will use for the testnet, it can be found in the section "account details" then "private key" in your metamask

### All smart contracts are deployed, you can verify the transaction in the explorer 
#### https://l2explorer.a1.taiko.xyz/
## 2. Noda
#### Install the dock, start it and check it 
```
curl -f -s -S -L https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
sudo systemctl status docker
```
### Clone this repository
```
git clone https://github.com/taikoxyz/simple-taiko-node.git
cd simple-taiko-node
```
### Configure your node 
```
cp .env.sample .env
```
### Next, replace the data in the .env file with your own, they are at the very bottom if you open it through a text editor: 
#### ENABLE_PROPOSER to true (replacing the default false with true)
#### L1_PROPOSER_PRIVATE_KEY to that of your wallet's private key -- it will need some balance on layer 1 to propose blocks. 
#### L2_SUGGESTED_FEE_RECIPIENT is just the address of your metamask to which the rewards will be sent. 

### Done after these steps, you can start the docker compose and the node is running congratulations 
```
docker compose up
```
#### The official website of the project read a lot of useful is : https://taiko.xyz/docs/alpha-1-testnet/start-here
#### Request ETH from Ethereum A1: https://l1faucet.a1.taiko.xyz/.
#### Request ETH from Taiko A1: https://l2faucet.a1.taiko.xyz/.
#### Deployed on L1: https://l1explorer.a1.taiko.xyz/address/0x3612E284D763f42f5E4CB72B1602b23DAEC3cA60
#### Deployed on L2: https://l2explorer.a1.taiko.xyz/address/0x0000777700000000000000000000000000000002
