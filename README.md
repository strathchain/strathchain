Strathchain
=========

> WARNING: Strathchain is intended for experimenting and learning, NOT for a production environment.

Strathchain is a private blockchain ecosystem preloaded with development tools, database, web & FTP servers and blockchain applications.

1. HashChain, a simple blockchain powered drag n drop solution for authenticating and verifying electronic records.
2. PrimeVault, a simple blockchain powered document storage and retrieval system.
3. PrimeContract, a simple blockchain powered system for digitally signng contracts.
4. StrathWallet, a simple blockchain powered wallet for Strathcoins, a smart asset.

This version of Strathchain runs on [Multichain](https://github.com/MultiChain).

Strathchain is ideal for

* Startups looking to quickly build a blockchain powered prototype, PoC or MVP.
* Serious researchers / enthusiasts looking to experiment with a live blockchain.
* In-house teams experimenting with blockchain technology.


System Requirements
-------------------

To set up Strathchain, you will need 1 server (min 2 GB RAM, 2 CPUs) running Ubuntu 16.04.2 x64 and php 7.0.

Installation
------------

This section presumes that you have root access to the server mentioned above and want to install Strathchain for all users on the system.

**Step 1.** Install git and clone the strathchain repository

    sudo apt-get install git
    sudo git clone https://github.com/strathchain/strathchain.git

**Step 2.** Harden the base operating system (Ubuntu 16.04.2 x64). This will also create a new user called strathuser with the password entered by you below.

    cd strathchain
    sudo bash -e hardening.sh <password>

**Step 3.** Install the FTP server. This will set up the FTP server. For logging in, use the IP address of your server as the `host`. The username and password are as entered by you below. The connection is `SFTP`.

    sudo bash -e ftp.sh <username> <password>


**Step 4.** Install, configure and run the Multichain blockchain, Multichain web-demo and Multichain Exporer. This also sets up HashChain, PrimeVault, PrimeContract and StrathWallet. The RPC port will be set as `9442` and the Network port will be set as `9443`. If you get a "locale error" using Terminal on mac, go to Terminal -> Preferences -> Profiles and uncheck "Set locale environment variables on startup"

    sudo bash -e multichain.sh <rpc-username> <rpc-password>
		
To access Multichain web-demo, visit `http://<IP Address>/multichain-web-demo`

To access Multichain Exporer, visit `http://<IP Address>:2750`

To use hashchain, see the instructions at [https://github.com/Primechain/hashchain/blob/master/README.md](https://github.com/Primechain/hashchain/blob/master/README.md)

To use PrimeVault, see the instructions at [https://github.com/Primechain/yobiapps/blob/master/README.md#primevault](https://github.com/Primechain/yobiapps/blob/master/README.md#primevault)

To use PrimeContract, see the instructions at [https://github.com/Primechain/yobiapps/blob/master/README.md#primecontract](https://github.com/Primechain/yobiapps/blob/master/README.md#primecontract)

To use StrathWallet, see the instructions at [https://github.com/Primechain/yobiapps/blob/master/README.md#yobiwallet](https://github.com/Primechain/yobiapps/blob/master/README.md#yobiwallet)


Notes
-----

This will:
1. harden the base operating system against cyber attacks

2. set up a Multichain blockchain using a pre-defined configuration

3. set up an FTP server

4. set up Multichain web demo

5. set up Multichain Explorer

6. set up HashChain, a simple blockchain powered drag n drop solution for authenticating and verifying electronic records.

7. set up PrimeVault, a simple blockchain powered document storage and retrieval system.

8. set up PrimeContract, a simple blockchain powered system for digitally signng contracts.

9. set up StrathWallet, a simple blockchain powered wallet for Strathcoins, a smart asset.

In case something goes wrong, you can roll back the multichain installation using

    bash rollback_multichain.sh 

Live demo
---------
* To access a live Multichain web-demo, visit http://52.172.209.229/multichain-web-demo

* To access a live Multichain Exporer, visit http://52.172.209.229:2750

* To authenticate a file using hashchain, visit http://52.172.209.229/hashchain/hashchain_authenticator.php and to verify a file using hashchain, visit http://52.172.209.229/hashchain/

* To access the apps, visit: http://52.172.209.229/apps
