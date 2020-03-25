# Devices Management

TODO:
1. Devices can have also a zenroom keypair (used for communications)
2. Device can have permissions to access recipes

# Recipes Management

Move all recipes to /recipes

Structure should be
`/recipes/ping/did.json`
DID document with all the details on the recipe
```json
{
    "@context": "@",
    "id": "did:lor:lab:1233",
    "author": "did:lor:lab:3456",
    "services": {
        "ping" : {

        },
        "remote" : {

        }
    }
}
```
/recipes/ping/ping.js
```javascript
const doStep = (recipe) => {
    switch(recipe.currentStep) {
        case "1": // whatever
    }
}
```
/recipes/ping/ping.json
```json
{
    "type": "send",
}
```
/recipes/ping/ping.js
```javascript
const doStep = (recipe) => {
    recipe.next("pong")
}
```
/recipes/ping/ping.test.js
```javascript
const doTest = (recipe) => {
    // assert()
}
```

/recipes/ping/remote.json
```json
{
    "type": "send",
    "to": "did"
},
{
    "type": "receive"
},
{
    "type": "send",
    "to": "cli"
}
```
/recipes/ping/remote.js
```javascript
const doStep = (recipe) => {
    recipe.next("pong")
}
```

## TODO

1. Move recipes to recipe folder
2. Do the tests for every recipe & integrate.
3. Manage recipes
    - Into Database : table recipes
    - install & uninstall recipes
    - Load only installed recipes
    - Keep track of all versions


# Steps Management

Separate every step into it's own file
/steps/start.js
/steps/start.test.js
/steps/send.js
/steps/send.test.js
/steps/receive.js
/steps/receive.test.js
/steps/ask_credential.js
/steps/ask_credential.test.js
/steps/verify_credential.js
/steps/verify_credential.test.js
/steps/call_api.js
/steps/call_api.test.js

/steps/index.js
```javascript
    // export all available steps

```

# GraphQL Module
Integrate into GraphQL
