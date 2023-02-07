# Concordium First Task

Mainnet Wallet: 3XK874y4R5QYaxHWwEoUmp9J3DqrknjBCuCD8qzD52Z5rrKvQM

## Install Rust and Cargo

First, you need to install rustup which installs Rust and Cargo on your computer. Go to Rustup to install rustup for your platform. https://rustup.rs/

![image](https://user-images.githubusercontent.com/39538184/217206288-d3145a45-7b3f-4316-bbbe-5c95e056d594.png)

Copy and paste the commands in a terminal to install Wasm which will be used for building contracts.

rustup target add wasm32-unknown-unknown

While installing Wasm on your system you should see something similar
to below.

![image](https://user-images.githubusercontent.com/39538184/217206484-331dcd08-09da-41c0-8d0c-07adc89b9d7c.png)

Now you need to install the Concordium software package. Click here https://developer.concordium.software/en/mainnet/net/installation/downloads-testnet.html#cargo-concordium-testnet

Download the version 2.7.0 or greater of cargo-concordium for your operating system. The tool is the same for both testnet and mainnet.

First, rename the cargo-concordium-v.x.x file to cargo-concordium. 

The tool should be placed in your PATH. This can be achieved by either:

Moving the executable to a folder that is already on your PATH, for example %HOMEPATH%\.cargo\bin\ for Windows, and $HOME/.cargo/bin for MacOS/Linux.
Or, by adding its current location to your PATH environment.

If everything is correct, when you enter the command cargo concordium --help it shows something similar to the below.

![image](https://user-images.githubusercontent.com/39538184/217206767-9e095219-3ef5-4275-b027-a624487fc4eb.png)

## Install Concordium Client

The tutorials use concordium-client as a command line tool to deploy, mint, and transfer. Download it here: https://developer.concordium.software/en/mainnet/net/installation/downloads-testnet.html#concordium-node-and-client-download-testnet. 

Rename the package to concordium-client in case it has some version annotation.

Check the installation and connect to the testnet node

Check whether you can run concordium-client with the following command:
- concordium-client --help

## Setup a wallet

Now you need a Concordium wallet. Use the Concordium Wallet for Web: https://chrome.google.com/webstore/detail/concordium-wallet/mnnkpffndmickbiakofclnpoiajlegmg?hl=en-US

The Concordium Wallet for Web uses a 24-word secret recovery phrase to secure your wallet. Make sure to protect your 24-word secret recovery phrase and store it in a secure place. Anyone who knows the secret recovery phrase can access your wallet.

Configure it to run on testnet with an identity created from the Concordium testnet IP (shown below) and an account based on that identity. 

You don’t have to provide an ID to create an identity on testnet when selecting Concordium testnet IP. Test identities are only available on testnet.

![image](https://user-images.githubusercontent.com/39538184/217207499-80d13572-a3e4-4245-a428-4005d020cc86.png)

Use the Testnet faucet in your account to claim 2000 CCDs for testing purposes.

When you have created your account and claimed your CCD, you will need to export the keys from your wallet. Save the file on your local machine in the same folder as the rest of the repository. It will have a name like this  <YOUR PUBLIC ADDRESS>.export. You can open it with a text editor and see your signKey and verifyKey in there. 

![image](https://user-images.githubusercontent.com/39538184/217207675-7a9010e3-d941-4ab2-9a2f-b11c77d95838.png)

## Import the key

You are ready to import your key into the concordium-client configuration. Move your "YOUR PUBLIC ADDRESS".export to the path where you are running your concordium-client tool. Navigate to the folder as well.

Import your key into the concordium-client configuration:

concordium-client config account import "YOUR PUBLIC ADDRESS.export" --name "Your-Wallet-Name"

Where "Your-Wallet-Name" is the name that you want to give to your wallet, which is the name you can use later when interacting with the account through the client.

![image](https://user-images.githubusercontent.com/39538184/217207992-87e4edc5-f0e0-437d-9547-0b2ba04d52a9.png)

And you are ready to deploy your contracts.

Happy coding!


