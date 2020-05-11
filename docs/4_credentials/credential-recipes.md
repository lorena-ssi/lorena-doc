# Credential recipes

## Credentials
The Lorena IDspace has built-in recipe support for Credentials of two types: a **Certificate Credential** which is a privately issued credential for an individual, and a **Badge Certificate** which is a publicly issued credential for an organization.

### Credential Certificate
Examples:
* An academic or professional credential, such as a degree or a license
* Completion of a course

### Badge Certificate
Examples:
* ISO 9001 Compliance

## SDK Usage Examples
Assuming you have connections to the IDspace through the SDK (see [Getting Started](../3_getting_started/contact-sdk.md))
* `adminSession`: has `admin` role in the IDspace, and `adminLinkId` is the link to use.

## Create

Before issuing a credential, first you must create it.

```javascript
const result = await adminSession.callRecipe(
  'credential-add', {
    credential: {
      title: `ISO 9001 Compliance`,
      description: `The organization meets ISO-9001 requirements`,
      url: `http://iso.org/certificate/iso-9001`,
      expiration: 'expires',
      startDate: '2020-05-01',
      endDate: '2021-05-01',
      requirements: 'Met all of the criteria for full ISO 9001 compliance',
      'badge'
    }
  }, adminLinkId)
```

## List
To retrieve a list of credentials created:

For `badge` type credentials:

```javascript
const result = await adminSession.callRecipe(
  'credential-list', { filter: 'badge' }, adminLinkId)
```

For `certificate` type credentials:

```javascript
const result = await adminSession.callRecipe(
  'credential-list', { filter: 'certificate' }, adminLinkId)
```

## Get

To get the details for a specific credential:

```javascript
const result = await adminSession.callRecipe(
  'credential-get', { credentialId: certificateId }, adminLinkId)
```

## Issue

Having created the credential, you can now issue it.

```javascript
const result = await adminSession.callRecipe(
  'credential-issue', {
    holder: {
      credentialId: certificateId,
      email: 'subject.email@email.domain',
      name: 'The Name of the Subject'
    }
  }, adminLinkId)
```
## List Issued Credentials

You can get a list of credentials issued for a specific credential.

```javascript
const result = await adminSession.callRecipe(
  'credential-issued', {
      credentialId: certificateId,
  }, adminLinkId)
```

## Verification

Credentials can be verified by using the website https://verify.lorena.tech, or through this SDK function:

```javascript
const result = await adminSession.verifyCertificate(json)
```