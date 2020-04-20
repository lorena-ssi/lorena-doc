# Your first contact using Lorena CLI

Your terminal is ready, and you are admin for your organization.
Two identities have been created : organization and persona (you).

## Adding more members

Open a new terminal with a different username and create a new Identity from a different member of the organization.
Ask to be a member of the organization.

```bash
./terminal
username: developer
password : god
lorena# info
{
    ....
}
lorena# link-member-of
DID: <OrgDID>
matrixUser: <OrgMatrix>
```



And from the admin terminal you can now connect with the new identity

```bash
lorena# rooms
[ Your rooms]
lorena# ping
RoomID : <roomID>
ping...done - 1 results
pong
```

You can see your new roomID (the identifier of the room), and the details for that room. Now you can also do a ping. It's time to ask to become a member of the organization. And reclaim your role as admin.

```bash
lorena# member-of
roomID: <IDSpace roomID>
extra: <extra information>
roleName : <admin/>developer/...>
```

The IDSpace will verify the self-signature to make sure you own your public key and the signature is Ok.

Also a challenge will be done to the DID of the IDSpace to verify other's side keys. key signature verification is done in both sides.

```bash
lorena# member-of-confirm
roomID: <IDSpace roomID>
secretCode: <secretCode>
```

If you use the secretCode generated for the first time. You will get admin role (roleName is ignored) and that code won't ever be available.

Now you are admin.

```bash
lorena# ping-admin
roomID: <IDSpace roomID>
lorena# member-list
roomID: <IDSpace roomID>
```
