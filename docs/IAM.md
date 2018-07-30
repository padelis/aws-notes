# Identity & Access Management

- IAM is universal.
- Root account has complete admin access.
- New users have **no permissions by default**.
- New users are assigned **Access Keys** and **Secret Access Keys**.
- You have to create passwords for new users.
- You can use Access Key and Secret Access Key to communicate wth AWS via console and SDKs.
- You can create password rotation policies.

## Groups

A way to group users and roles and apply Polices.

## Roles

All roles are global.

## Security Token Service

Grants users limited and temporary access to AWS resources. User can from three sources:

- Federation
  - Uses Security Assertion Markup Language (SAML)
  - Active directory credentials
- Federation with mobile apps
- Cross Account Access

1.  Identity Store (Facebook)
2.  Identity Broker (join Identity from point A to point B)

A call to Security Token Service federation actions returns:

1.  Access Key
2.  Secret Access Key
3.  Token
4.  Expiration

_Avoid storing credentials locally_.

## Policies

Docs that define permissions in JSON. Key-Values Documents

```
{
  "Version": 2018-10-17,
  "Statement":
  [
    {
      "Effect": "Allow",
      "Action": "*",
      "Resource": "*"
    }
  ]

}
```
