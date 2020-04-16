# Installation

Lorena is a secure and private peer-to-peer identity middleware. Following the installation guide you will be available to start coding [recipes](../2_overview/recipes.md), connecting with other Lorena identities and that's just the beginning!

Let's start with our first Lorena ID:
## 1. Get an invite!
Currently, we have a by-invitation only environment. First thing you have to do is to ask us for an invitation to [this Riot room](https://riot.im/app/#/room/!euLDblFPfxcoBjSRBM:matrix.org?via=matrix.org), ask for @alex or @diego and tell us why do you want to test Lorena for. We will setup an [IDSpace](../2_overview/idspaces.md) for you and we will add you as admin for that IDSpace and send you via PM :
- The new IDSpace DID
- The matrix User for that DID
- a secretCode to connect with your IDSpace

You will use it later ;)

## 2. Install Lorena SDK and Terminal
Download https://github.com/lorena-ssi/terminal:
```bash
$ git clone https://github.com/lorena-ssi/terminal
$ cd terminal
$ npm install
```

To improve your experience using Lorena CLI we coded a terminal App that should be of use to learn on who to use the SDK.

The terminal is an example on how to use Lorena SDK. It will help you understanding the basics of Lorena and how to interact with tour IDSpace.

## 3. Running Lorena CLI
The first time you run it will prompt you to create a new Wallet. 

Execute CLI
```bash
$ ./terminal
Lorena Client

Username :<username>
Password :<pass>
A Wallet for username Does not exist
Create One (Y/n)
```

**What happened so far** : The user and password are used to securely store all of your information locally. Your new wallet can be STORED in your FS (|~/.lorena/wallets/user) or in LocalStorage if you are working with the SDK from the Browser.

Now you can fill in your data. Remember your profile details will be stored locally and never sent anywhere else without your explicit consent.

```bash
Key Pair + DID Added
First Name :John
Last Name (1) :Smith
Last Name (2) :Sikaris
DNI :1111111A
Phone number :55566744
Email :john@test.com
City/Town :Barcelona
Postal Code :08001
Neighborhood :El Born
Save Storage
```

**What happened so far** : Your wallet is ready with a new matrix user for P2P communications.

So now you just set up your first Identity Wallet and you are ready playing with it.
Try to get information using these commands:
```bash
lorena# help
[ list of actions ]
lorena# info
{
  matrixUser: <matrixUser>,
  matrixPass: <matrixPass>,
  blockchainServer: 'wss://labtest.substrate.lorena.tech',
  matrixFederation: 'labtest.matrix.lorena.tech',
  matrixServer: 'https://labtest.matrix.lorena.tech'
}
```

As you can see you are not connected to the IDSpace. Try to run rooms (your connections). It's empty. Let's connect to our own IDSpace


