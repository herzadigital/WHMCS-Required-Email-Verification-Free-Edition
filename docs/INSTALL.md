# Installation, configuration and removal

## Installation

1. Verify the installation ZIP against downloads/SHA256SUMS in the repository.
   Inside the ZIP, SHA256SUMS covers its payload and manifest.
2. Check COMPATIBILITY.md. Back up the WHMCS application, database and matching
   encryption configuration; prove restore separately.
3. Extract outside the public web root. Upload only modules/ and includes/
   into WHMCS. Do not upload documentation, license or manifests into web root.
4. Open Configuration > System Settings > Addon Modules (menu names may vary).
   Activate **WHMCS Required Email Verification - Free Edition** and grant the
   intended administrator roles.
5. Leave **Enable Email Verification** disabled while preparing staging.
   Configure Client Area Gate, Checkout Gate, First Client ID, Allow OTP Email
   Sending and Audit Retention.
6. Set First Client ID to 1 for all accounts, or a reviewed higher boundary.
   It includes every higher ID and future accounts, not just one test account.
7. Configure and test the native mail provider in WHMCS General Settings > Mail.
   Keep SMTP/API credentials in WHMCS; the addon does not need separate ones.
8. With a permitted mailbox, test unverified login/checkout, wrong/expired/used
   OTPs, successful verification, logout/login and a native owner email change.
   Then deliberately enable the selected gates and email sending.
9. Keep native WHMCS daily cron configured for bounded retention cleanup.

WHMCS **Disable Email Sending** also blocks OTP handoffs. The addon never clears
a global or addon sending stop automatically. The per-installation secret is
generated using native WHMCS encryption. Preserve that encryption configuration
with its database; never regenerate a secret over existing verification records.

## Pause and removal

Pause Allow OTP Email Sending to stop new handoffs. Verified owners retain their
status. Disable Enable Email Verification to stop both gates, or deactivate the
addon through Addon Modules. Deactivation preserves data.

After deactivation remove only modules/addons/herza_email_verification and
includes/hooks/herza_email_verification.php when uninstalling. Removal of
mod_hrev_meta, mod_hrev_otp, mod_hrev_limits and mod_hrev_audit is a separate,
deliberate retention decision after backups. Do not clear native owner flags.

## Recovery and customization

Do not mix files from different packages. If installation fails, inspect web
PHP/Loader versions, complete upload, DB permissions and native encryption.
Activation can leave empty tables after a DDL failure; do not delete retained
records blindly. Keep enforcement/sending stopped while investigating.

Restore a complete reviewed file set when appropriate; retain the current
database, secrets, revocations and consumed OTP state. A stale DB restore can
revive invalid proof and is a separate recovery incident, not normal code rollback.

Language catalogs in lang/ and clientarea.tpl are intentionally readable.
Keep catalog keys, placeholders, PHP syntax and template escaping intact.
Do not edit WHMCS core files. Back up any customization independently.

This Free Edition has no automatic updater and includes no future release
entitlement. Do not activate another Herza verification addon alongside its
gates. It shares its addon ID with the commercial email-only product; no automatic
migration from the separate internal Email & Phone product is supplied.
