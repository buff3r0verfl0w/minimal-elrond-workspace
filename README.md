# minimal-elrond-workspace
This is minimal example how to setup almost empty smart contract on elrond network

### Requirements
 - erdpy: https://docs.elrond.com/sdk-and-tools/erdpy/installing-erdpy/
 - elrond IDE for vscode: https://youtu.be/bXbBfJCRVqE
 - PEM wallet on testnet
   ```bash
   mkdir -p adder/wallets/users
   cp /path/to/wallet-owner.pem adder/wallets/users/alice.pem
   ```
### Interaction with smart contract
Please watch the video, it should explain

 - using bash and vscode plugin, **make sure that you're using testnet**
 - using python3
   ```bash
   cd adder
   python3 interaction/playground.py --pem wallets/users/alice.pem
   ```
