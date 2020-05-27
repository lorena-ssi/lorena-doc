# Managing Lorena Webapp

In this tutorial we will show how to manage your wallet with our webapp: https://lorena.app.test.caelumlabs.com/. We are going to show you how to create a webapp Wallet (Admin for Desktop and User for Mobile), create credentials, scan/share  QR codes and administrate an IDSpace. When using Lorena webapp you can have several wallets, and access them simultaneously from different terminals, web applications or new wallets. This might be useful because every wallet is associated to only one `network`, there can be many other `networks` live. Each wallet though, can be connected to several IDSpaces in the same `network` using `link`s. 

In this tutorial there we will be using one Lorena IDSpace that will be manipulated from Lorena webapp. This means Lorena Terminal will create a Wallet with your data, and it will be connected to Lorena IDSpace from our main subtrate `network`.

## Create your Lorena Mobile Wallet

Go to the url from a mobile browser and click on `REGISTER` button to start the process. 

![](../images/tuto2/1.png)

Fill your `username` and `pin` number, this one is a code to lock/unlock your wallet data of minimum 4 chars.

![](../images/tuto2/2.png)

Now you have set the wallet name and code, and next step is to fill Personal data information:

![](../images/tuto2/3.png)

Finally, accept legal and privacy terms to finish your wallet registration. Now you have connected with the IDSpace and you are waiting for the `secret code`. That code is in charge of the IDSpace admin. Admin has the control of the users that can add or not others. So let's go to see admin dashboard ;)

![](../images/tuto2/4.png)

Remember to keep the browser opened!

## Let's play as Admin

In order to control the IDSpace, you have to download the admin wallet: 

[adminlorena_wallet.json](../images/adminlorena_wallet.json)

Now, from a desktop browser open the url and click on `IMPORT WALLET`.

![](../images/tuto2/4a.png)

Select from the dropdown `adminwallet` and the pin code `admin123`.

Now you can manage Lorena IDSpace, the menu options you have are Home (current), Services, Contacts, Credentials and Profile.

![](../images/tuto2/5.png)

In our case, we have to visit Contacts:

![](../images/tuto2/6.png)

Here we see the list of verified contacts and list of requested contacts, where our request from mobile user wallet is waiting for:

![](../images/tuto2/7.png)

You can see the requester, diego with rolename member has the status `requested` for that role. At the end, there is the a code called `secretcode`. This is the code User needs to be a member of that IDSpace. In other environment, admin's will send that code to the user, but now we are learning how to accept other members being members of the IDSpace.

Now, introduce the secret code `16458795` for the `Diego Nine` user to the mobile wallet and go on:

![](../images/tuto2/7.png)

![](../images/tuto2/8.png)

Congratulations! You have created your first Lorena Wallet linking it with the IDSpace.

## Show me the QR

If you want to connect and know info about any user, you just have to share/scan the QR code. Following the tutorial, from the user mobile wallet show your QR code:

![](../images/tuto2/9.png)

Now, with you mobile user webapp wallet, scan it:

![](../images/tuto2/11.png)

![](../images/tuto2/12.png)

If you accept sharing your data, it will appear on the admin webapp wallet like this:

![](../images/tuto2/13.png)

Hey!! Sharing your personal data compliance with GDPR is supereasy! Let's control back user data :-)


## Who said credential is hard?

Nowadays, credentials are important to verify actions, documents, processes,...with Lorena you have it as easy as this:

From Admin WebApp, let's create a new type of credential from menu option:

![](../images/tuto2/14.png)

![](../images/tuto2/15.png)

![](../images/tuto2/16.png)

![](../images/tuto2/17.png)

Great! We can customize it as we wish. Now, let's issue one [Verifiable Credential](../2_overview/credentials.md) to our user `diego9`. We have to put the credentialID just created (image above) and, in the `email` field, put your email to receive your fist credential :D

![](../images/tuto2/18.png)

![](../images/tuto2/19.png)

Did you believe that? Check your email, get your credential and verify it in our platform copying the json content and pasting in the following url [https://verify.test.lorena.tech](https://verify.test.lorena.tech).

Alright! Now you can start issuing Veriable Credentials and verify them as many as you want :D


## Updating user roles

From the Admin Webapp Wallet, we can change user roles just clicking on here:

![](../images/tuto2/20.png)

Let's check our user wallet from the smartphone:

![](../images/tuto2/21.png)

Here we go! Now I'm admin too from my mobile wallet :)

Amazing! Now can manage our users as we wish!