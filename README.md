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

### How to create project from template?
```bash
PROJECT_NAME=project1

to_title_case() {
  sed 's/.*/\L&/; s/[a-z]*/\u&/g' <<<"$1"
}
PROJECT_NAME_TITLE_CASE=$(to_title_case $PROJECT_NAME)

git clone git@github.com:buff3r0verfl0w/minimal-elrond-workspace.git
cd minimal-elrond-workspace

rm -rf .git
rm README.md
rm -rf erdjs-snippets
rm adder/interaction/Adder.erdjs.md

sed -i -e 's/Adder/'$PROJECT_NAME_TITLE_CASE'/g' adder/src/adder.rs
find ./ -type f -exec sed -i "s/adder/$PROJECT_NAME/g" {} \;

mv adder $PROJECT_NAME
cd $PROJECT_NAME

mv tests/adder_mandos_go_test.rs tests/$PROJECT_NAME_mandos_go_test.rs
mv tests/adder_mandos_rs_test.rs tests/$PROJECT_NAME_mandos_rs_test.rs
mv tests/adder_test.rs tests/$PROJECT_NAME_test.rs
mv src/adder.rs src/$PROJECT_NAME.rs
mv mandos/adder.scen.json mandos/$PROJECT_NAME.scen.json

cd ..
```
