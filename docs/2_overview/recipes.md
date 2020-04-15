# Credential Recipes

Credential Recipes are the way ID Spaces talk to each other. The process can look like this:
2. Alice ID Space Connect to Bob's (using Bob's DID)
3. Bob accepts Alice Connection and it's GDPR conditions (how data will be shared and used)
4. Alice asks Bob for a Credential : EmailVerification
5. Bob Sends an email to Alice with an unique random number
6. Alice sends the number to Bob
7. Bob Creates the credential and sends it to Alice
Alice stores the credential on her own Database in the IDSpace

# Recipes
## Recipes Lifecycle
### Create
### Update
### Looking up
### Integrations
## Recipes Identifiers
## Consent Management Recipes
### Privacy Policy
### Service Policy
### Data Collection
### Consent recipe
#### Storage
#### Search
## Lorena SDK
## Lorena Terminal