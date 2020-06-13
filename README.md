# AVA Command Line Tool

AVA bash script running on both Linux and MacOS. (Tested on Ubuntu 20 and MacOS Catalina)

Required components:
* AVA Node (Installation: https://docs.ava.network/v1.0/en/quickstart/ava-getting-started/ )
* curl
* jq
* sed
* awk

**Capabilities**
* Create user
* Create P-Chain Account on default subnet
* Stake x AVA for y days
* Stake issued but not staking balance
* Check active and pending validators and your node's validator status

**USAGE:**

**_Before running the script, edit settings.txt and at least add a username and password_**

$ sh avacmd command parameter1 parameter2

or

$ avacmd command parameter1 parameter2

> Give execution permission to file with **chmod a+x avacmd** and add path to your $PATH with **export PATH=${PWD}:$PATH** to be able to run script directly

Available commands:
Command | parameter1 | parameter2 | Description
-------------|-------------|-------------|-------------
balance|||Get AVA balance of your AVA address
balanceall|||Get all asset balances of your AVA address
createuser|default||Creates your user with the defined username and password in settings.txt
createuser|username|"strongpass"|Creates the user with the given password. Password must be at least 8 chars including a lowercase, an uppercase, a number and a special character
deleteuser|username|"strongpass"|Deletes the user (Warning: Use with caution)
fundsubbet|amount|days|Fund default subnet with the given amount and start staking for given days. If no amount is set, it uses all available balance (-100AVA). If no stake length (in days) set, staking length will be 30 days
issuedbalance|||Get balance issued to P-Chain address
listpaccounts|||List all accounts on P-Chain
nodeid|||Get your NodeID
users|||List users
pendingvalidators|||List pending validators on default subnet
pendingvalidators|onlyme||List if your node is in pending validators on default subnet
stakeissued|days||Stake issued but not staked balance for given days on P-Chain address
tx|TXID||Get result of the given transaction (TXID mandatory)
validators|||List active validators on default subnet
validators|onlyme||List if your node is in active validators on default subnet

**Settings.txt**

Variable|Description
-------------|-------------
USERN|Your node username
PASSW|Your node user password
NODEID|Your Node ID (leave blank if you don't know)
AVAADR|Your AVA address (leave blank if you don't know)
PCHAIN|Your P-Chain Account (leave blank if you don't know)
HOST|AVA Node's Host or IP
PORT|AVA Node's HTTP Port
STAKEL|Stake length (30 Days by default. You can set when using fundsubnet command)

*Feel free to share your comments*
*Send your questions using Issues section*

#### Use for testing purposes on Denali Testnet. Do not use on mainnet (when launched)