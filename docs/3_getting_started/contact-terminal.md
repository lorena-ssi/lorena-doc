# Your first contact using Lorena Terminal

! Remember you should finished [installation](installation.md) to continue with tutorial, you need a _connection string_ and _PIN code_ to continue:

Now, with your terminal running like this:

You can start playing a bit, lets check all commands you can try. Remember, all that commands are recipes and you can create yours in this [installation](create-recipes.md).

Let's add your first contact. We will connect with the IDspace we just created for you. You already have the DID, matrixUser and secretCode, now you will use them.

## Connect with your IDspace

### Create a room

```bash
lorena# room-add
DID : <IDspace DID>
matrix : <IDspace matrixUser>
Created room: !tkdjQmQMgYCjznnfgW:labtest.matrix.lorena.tech
Successful
Contact invitation Accepted from ztbjrel4b1lh:labtest.matrix.lorena.tech
```

You added this new room to your list of rooms (stored encrypted in your wallet)
When you quit the terminal it will ask to save all the changes to your Wallet.

```bash
lorena# rooms
[ Your rooms]
lorena# ping
RoomID : <roomID>
ping...done - 1 results
pong @slvlnetgenrq:labtest.matrix.lorena.tech
```

You can see your new roomID (the identifier of the room), and the details for that room. Now you can also do a ping. It's time to ask to become a member of the organization and claim your role as admin.

## Claiming Admin role

The IDspace will verify the self-signature to make sure you own your public key and the signature is OK. Also a challenge will be done to the DID of the IDspace to verify other's side keys. key signature verification is done in both sides.

There are two ways to claim a role of admin in an organization:

### IDspace init secret code

If you use the `secretCode` generated when the IDspace is created (`./IDspace init`). This is useful only once: that code won't be usable again.

```bash
lorena# member-of
roomID: <IDspace roomID>
extra: <secretCode>
roleName : admin
```

```bash
lorena# member-of-confirm
roomID: <IDspace roomID>
secretCode: <secretCode>
```

### New admin request

If you want to add an additional identity as admin of an IDspace you can use `member-of` and `member-of-confirm`.

```bash
lorena# member-of
roomID: <IDspace roomID>
extra: <blank>
roleName : admin
```

The IDspace log will show the secret code needed to confirm the admin request. Call `member-of-confirm` with that secret code.

```bash
lorena# member-of-confirm
roomID: <IDspace roomID>
secretCode: <secretCode>
```

## Viewing roles

```bash
lorena# member-list
roomID: <IDspace roomID>
```

You can see your identity listed with the `admin` role.