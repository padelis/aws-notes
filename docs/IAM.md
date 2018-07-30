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
Avoid storing credentials locally.

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
