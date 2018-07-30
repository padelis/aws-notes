# AWS Organizations

AWS Organizations is an account management service that enables you consolidate multiple accounts into an organization that you create and centrally manage.

Available in two feature sets:

1.  Consolidated billing
2.  All features

## Tips

- **20 accounts** default limit
- One bill per account
- Very easy to track things
- Volume pricing discount
- Billing Alerts (all linked accounts included)
- Unused reserved instances for EC2 are applied across the group.
- CloudTrail - Per AWS account and per region (can be aggregated in to a single bucket in the paying account)

## Best Practices

- Always enable multi-factor authentication on the root account
- Always use a strong password on the root accounts
- Paying account should be used for billing only. Do not deploy resources in to paying account.

## Cross Account Access

You can login in the console with the IAM username, then switch the console to manage another account.
