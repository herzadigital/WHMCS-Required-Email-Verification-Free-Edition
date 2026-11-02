# Security and operational boundaries

This Free Edition is limited to version 1.0.0; no future fixes or updates are
promised. Check this repository for security notices or withdrawal notices
before installing. Do not use a package identified as unsafe.

Use isolated staging and a restorable backup first. Protect WHMCS configuration
and database together: the module stores its per-installation secret using
native WHMCS encryption. Never reset the secret or restore old verification
flags merely to make an error disappear.

Only the current authenticated main owner may request/submit their OTP. Native
owner email changes invalidate previous challenges/proof and require fresh
verification. Direct SQL user edits that bypass WHMCS hooks are unsupported.
This is email ownership verification, not login 2FA or universal API authorization.

OTP digests/keyed contact identifiers and audit metadata are stored; plaintext
OTPs are not deliberately logged or stored in module tables. The configured
mail provider necessarily processes the message. Avoid email-body/request-body
debug logging and redact diagnostic evidence.

Both addon and native WHMCS sending stops apply. A successful handoff is not
proof of inbox delivery. Uncertain results do not trigger automatic retry.
Persistent account/email/IP quotas remain consumed after a claimed handoff.

Never post passwords, OTPs, private keys, configuration.php, provider credentials
or a customer database in public issues. Contact Herza through its official
website for a private security reporting route; personal support is not included.

Pause sending and enforcement or deactivate the addon when investigating.
Deactivation retains verification/audit records. Preserve current revocation
and consumed-challenge data during recovery. This package contains no SMS sender,
SMS callbacks, automatic updater or external license activation service.
