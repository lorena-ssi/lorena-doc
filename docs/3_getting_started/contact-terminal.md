# Your first contact using Lorena Terminal

You can start playing a bit, lets check all commands you can try.

Let's add your first link. We will connect with the IDspace we just created for you.

## Link to your IDspace

### Create a link

```bash
lorena# link-add
DID : <IDspace DID>
matrix : <IDspace matrixUser>
Created room: !tkdjQmQMgYCjznnfgW:labtest.matrix.lorena.tech
Successful
Contact invitation Accepted from ztbjrel4b1lh:labtest.matrix.lorena.tech
```

You added this new link to your list of links (stored encrypted in your wallet). When you quit the terminal it will ask to save all the changes to your Wallet.

```bash
lorena# q
Save changes (y/n)

./terminal
lorena# links
[ Your links]
lorena# link-ping
RoomID : <roomID>
ping...done - 1 results
pong @slvlnetgenrq:labtest.matrix.lorena.tech
```

You can see your new roomID (the identifier of the link), and the details for that link. Now you can also do a ping. It's time to ask to become a member of the organization and claim your role as admin.

## Claiming Admin role

In the IDspace a challenge will be done to the DID of the IDspace to verify other's side keys. key signature verification is done in both sides.

There are two ways to claim a role of admin in an organization:

### IDspace init secret code

If you use the `secretCode` generated when the IDspace is created (`./IDspace init`). This is useful only once: that code won't be usable again.

```bash
lorena# link-member-of
roomID: <IDspace roomID>
Extra: <secretCode>
roleName : admin
```

```bash
lorena# link-member-of-confirm
roomID: <IDspace roomID>
secretCode: <secretCode>
```

### New admin request

If you want to add an additional identity as admin of an IDspace you can use `link-member-of` and `link-member-of-confirm`.

```bash
lorena# link-member-of
roomID: <IDspace roomID>
extra: <blank>
roleName : admin
```

The IDspace log will show the secret code needed to confirm the admin request, also if you are already an admin, you can call `link-member-list` to see the requests and its associated codes. Call now `link-member-of-confirm` with that secret code.

```bash
lorena# link-member-of-confirm
roomID: <IDspace roomID>
secretCode: <secretCode>
```

## Viewing roles

```bash
lorena# link-member-list
roomID: <IDspace roomID>
```

You can see your identity listed with the `admin` role.

## Approving additional members and roles

Other roles can be added to the organization with the same process as the New Admin Request, except instead of looking at the IDspace log, the admin looks at the `link-member-list` for the secret code, which the admin then transmits to the prospective member out-of-band.

* New member
  * creates a new session with `./terminal`, with a new username and password
  * creates a new room using `link-radd`
  * calls `link-member-of` with the role desired (e.g. `developer`)
* Admin
  * calls `link-member-list` to see information for the new member with status `requested`
  * gives the `secretCode` to the new member through a secondary medium (messenger, email, phone)
* New member
  * calls `link-member-of-confirm` with the `secretCode` given by the admin

The new member will now have the status `verified`.