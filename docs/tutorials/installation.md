# Installation

Lorena is a peer-to-peer security and private identity middleware. Following the installation guide you will be available to start coding [recipes](blockchain/substrate/recipes.md), connecting with other Lorena identities and whatever you can imagine!

Let's start with our first Lorena ID:
#### 1. Get an invite!
Currently, we have a closed environment with a maximum of 100 identities. First thing you have to do is to ask us for an invitation to this Riot room: https://riot.im/app/#/room/!euLDblFPfxcoBjSRBM:matrix.org?via=matrix.org, ask for @alex or @diego and tell us why you want to try Lorena.
If you get invite, you will receive two codes: Connection String and PIN number. You will use them later ;)

#### 2. Install Lorena CLI
Download https://github.com/lorena-ssi/lorena-cli:
```bash
$ git clone https://github.com/lorena-ssi/lorena-cli
$ cd lorena-cli
$ npm install
```

#### 3. Running Lorena CLI
Execute CLI
```bash
$ ./terminal addadmin
```

Now, you have to set your username and password and fill the connection string and pin code you got in step 1:
```bash
Username :_username_
Password :_password_
Connecting...Creating new connection
Connection String :bDN9bOyhNUUvO9BYJvyR4w-!-NDM2ZjZlNmU2NTYzNzQ2OTZmNmUyMDUzNzQ3MjY5NmU2Nw-!-vbr73nDBh
75IpwdPzhBWvEiqDmjXS-TGkdlrtKy3bmI-!-V0jzfrK3lcB9Fc1v0qacVPmP6wPmAYrillA6qAhJqXf_ez0gQVF0LsPibobXlOD40
YRhmWGXPNDNOZZS0RhG_pUDseyts2v8a1JHjjT7kJBUgNnYfvevur7WBwNXuT5iTk5zOilhoE1ms9bRZ4kieDQqikpa70HID7DwVMV
IsAMcshjsCZfqFu_eLDtJz35M0bd_UqyFJcfhp-gJYntWv_MLfEpFtI7W2bIYTvgIltrd6Qqqb57dzWuLrwlRNx_Edn3B0eyCKlWFn
MTP-3Ffr7nUi6dW2zJ6DWs9KkSlKRmtbTdWRQ1LIyxOQlX7wIuna8qG07-9
PIN :_pincode_
```
When the process finishes, you will promtp in Lorena CLI. Try help to see the functions available:

```bash
lorena# help
actions :
[
  'info',           'exit',
  'help',           'pubkey',
  'ping',           'ping-remote',
  'ping-admin',     'contact-list',
  'contact-invite', 'contact-add',
  'contact-info',   'peer-add',
  'peer-list',      'contact-handshake',
  'recipe-list'
]

```
and finally, you can try _help_ to see your personal data:

```bash
lorena# info
info :
{
  matrixUser: 'q1rfmnhvem9v',
  matrixPass: 'TFhTeFBLQWVN',
  did: 'Y20xM01Xc3hjMmRuVUhCbUxYVlFNMmR1',
  roomId: '!nSxVKpjMXmeWxTQtUl:matrix.caelumlabs.com',
  keyPair: { diegotorres: { keypair: [Object] } },
  username: 'diegotorres',
  matrixServer: 'https://matrix.caelumlabs.com',
  matrixFederation: ':matrix.caelumlabs.com',
  blockchainServer: 'wss://substrate-demo.caelumlabs.com',
  didMethod: 'did:lor:lab'
}

```