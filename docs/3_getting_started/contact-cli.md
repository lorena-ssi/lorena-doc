# Your first contact using Lorena CLI

! Remember you should finished [installation](installation.md) to continue with tutorial, you need a _connection string_ and _PIN code_ to continue:

Now, with your terminal running like this:

You can start playing a bit, lets check all commands you can try. Remember, all that commands are recipes and you can create yours in this [installation](create-recipes.md).

Let's add your first contact. We will connect with the IDSpace we just created for you. You already have the DID, matrixUser and secretCode, now you will use them.

## Connect with your IDspace

```bash
lorena# link-add
DID : <IDSpace DID>
matrix : @ztbjrel4b1lh:labtest.matrix.lorena.tech
Successfull
Contact invitation Accepted from ztbjrel4b1lh:labtest.matrix.lorena.tech 
```

You added this new link to your list of links (stored encrypted in your wallet). When you quit the terminal it will ask to save all the changes to your Wallet.

```bash
lorena# links
[ Your rooms]
lorena# link
RoomID : <roomID>
{link Information}
lorena# link-ping
RoomID : <roomID>
ping...done - 1 results
pong
```

You can see your new roomID (the identifier of the room), and the details for that room. Now you can also do a ping. It's time to ask to become a member of the organization. And reclaim your role as admin.

```bash
lorena# link-member-of
roomID: <IDSpace roomID>
extra: <extra information>
roleName : <admin/developer/...>
```

The IDSpace will verify the self-signature to make sure you own your public key and the signature is Ok.

Also a challenge will be done to the DID of the IDSpace to verify other's side keys. key signature verification is done in both sides.

```bash
lorena# link-member-of-confirm
roomID: <IDSpace roomID>
secretCode: <secretCode>
```

If you use the secretCode generated for the first time. You will get admin role (roleName is ignired) and that code won't ever be available.

Now you are admin.

```bash
lorena# link-ping-admin
roomID: <IDSpace roomID>
lorena# link-member-list
roomID: <IDSpace roomID>
```
