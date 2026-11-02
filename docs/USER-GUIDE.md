# Using email verification

Sign in as the main account owner. When prompted, check the masked owner email,
request a code and enter the six digits from that mailbox. Codes expire after
five minutes and permit five failed attempts. Wait at least 60 seconds before
requesting another code. Use the newest code and current form.

After success, continue to Client Area or your cart. Logout/login should retain
verification for the same current owner email. Changing the owner's login email
through native WHMCS actions makes it UNVERIFIED and invalidates the former
address's proof/OTP, including when changing back. The edit does not itself send
a code; request a fresh code for the new address.

The owner login email may differ from billing email. Billing/additional contacts
do not verify the owner's address. Use Switch account or Sign out when the
correct main owner must sign in.

## Troubleshooting

- Check spam/junk, the masked recipient and the native WHMCS provider settings.
- After an uncertain handoff, inspect the inbox before requesting a replacement;
  no automatic retry follows an ambiguous outcome.
- Shared office/VPN IPs share request limits. Do not clear quota records to bypass
  limits. Refresh after a stale-form message or account/session change.
- A verified page after Back or an old POST is an idempotent view, not a second
  acceptance of a consumed OTP.
- If an address is inaccessible, contact your hosting provider's authorized team.
- For Loader errors, inspect the actual web PHP/Loader; CLI can use a different
  version. Read the compatibility matrix before installing.
- Never provide passwords, OTPs, encryption keys or full configuration/database
  files through public issues.

Only email verification is available. SMS and upgrades, including v2.0.0, are
not included. Public documentation is provided without personal support.
