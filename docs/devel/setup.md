# Setup Lorena
### What do you need to have a ID Space up.

## Setup
First you need to install IPFS (Installation) or you can use a public IPFS node

You can also install your own Substrate Node or use a Public One.

```bash
$ ipfs daemon &
$ export SERVER_MATRIX=https://matrix.caelumlabs.com
$ export SERVER_SUBSTRATE=wss://substrate-demo.caelumlabs.com/
$ export PDS_PASSWORD=secret_pass
```

Substrate is the only Blockchain supported but we are working to integrate more in the near future.

Ready to init your first IDSpace. We are using the organization name caelum, but you can choose your own. This will setup your keys, matrix user and blockchain connection.

```bash
$ ./idspace init caelum
```

Check your DID document has been created to IPFS : https://ipfs.io/ipfs/<ipfsHash>

Now you can add a client to your ID Space.

```bash
$ ./idspace add_client caelum caelum-cli
```

Now you have new matrix user connected as a client to your ID Space. You can now send commands to it. Start the ID Space:

```bash
$ ./idspace caelum
```