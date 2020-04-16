# Setup Lorena

IDspace : Identity Container allowing Recipes to be automated and Executed.

Lorena SDK : Identity Container in the Browser, Mobile App or as an external node App. Uses Local Storage or Local Filesystem.

Substrate is the only Blockchain supported but we are working to integrate more in the near future.

### What do you need to have a ID Space up.

We already have a few IDspaces for test running. If You want onw you just need to ask for one. We will add you as admin for it.

You can ask for one IDspace in [our Matrix Channel](https://matrix.to/#/!euLDblFPfxcoBjSRBM:matrix.org?via=matrix.org)

## Setup

To interact with your IDspace, we will send you a Connection String and a PIN.

1. Ask for an IDspace at our Matrix Channel We will create one for each organization.
2. We will send you instructions on how to connect (connection string & PIN)
3. Install the Terminal.
4. Set a username & password.
5. Connect for the first time using the Connection String and the PIN.
6. Now you can talk to your IDspace.

You can use the terminal to play with your IDspace. Install it from :
```bash
$ git clone https://github.com/lorena-ssi/terminal
$ ./terminal
> username : yourname
> password : yourpass
> connString : connection string (sent to you)
> PIN : PIN (sent to you)
```

The connection string has encrypted instructions on how to connect to your IDspace. Including the DID, matrix User of your DID, and specific Blockchain being used.

Now you are connected to the terminal. You can test it

```bash
#lorena: help
#lorena: ping
```

The terminal itself is an example on how to use the Lorena SDK