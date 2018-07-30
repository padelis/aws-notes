# IAM

1.  Users
2.  Groups
3.  Roles
4.  Policies -> docs that define permissions. applied above

## Roles

All roles are global.
We dont have to store credentials locally.

## Security Token Service

Grants users limited and temporary access to AWS resources. User can from three sources:

- Federation
  - Uses Security Assertion Markup Language (SAML)
  - Active directory credentials
- Federation with mobile apps
- Cross Account Access

1.  Identity Store (Facebook)
2.  Identity Broker (join Identity from point A to point B)

A call to STS federation actions returns:

1.  Access Key
2.  Secret Access Key
3.  Token
4.  Expiration
