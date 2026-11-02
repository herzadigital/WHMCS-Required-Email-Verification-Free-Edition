# WHMCS Required Email Verification — Free Edition

**Version 1.0.0 · Author: Herza, Ltd.**

Require the main account owner to verify their current login email with a
six-digit OTP before accessing the Client Area or proceeding through checkout.
Email is sent through the mail provider configured in WHMCS.

**Free Edition 1.0.0 includes email verification only. SMS Verification is not
available.** Future updates, personal support and upgrades, including v2.0.0,
are not included. Any future Email & SMS product requires separate entitlement;
no SMS code, vendor integration or SMS development module is distributed here.

**Bahasa Indonesia:** Versi 1.0.0 ini gratis untuk digunakan sesuai
[ketentuan lisensi](LICENSE.md). Hanya Email Verification yang tersedia.
Tidak termasuk pembaruan, dukungan langsung atau upgrade ke v2.0.0.
SMS Verification masih dalam pengembangan dan tidak tersedia dalam paket ini.

## Download and install

Download [the encoded installation ZIP](downloads/WHMCS-Required-Email-Verification-Free-Edition-1.0.0-encoded.zip)
and verify [its SHA-256](downloads/SHA256SUMS). The ZIP is the installation package.
GitHub's **Code > Download ZIP** contains this distribution repository, not
directly installable WHMCS root files.

1. Read [compatibility](docs/COMPATIBILITY.md), [installation](docs/INSTALL.md)
   and [security boundaries](SECURITY.md).
2. Back up and test on an isolated licensed WHMCS staging installation.
3. Extract the installation ZIP outside the public web root. Upload only its
   modules/ and includes/ directories into your WHMCS root.
4. Activate **WHMCS Required Email Verification - Free Edition** through native
   Addon Modules, grant intended admin roles and configure the gates.
5. Verify delivery to a permitted test mailbox before enforcing broadly.

## Features and limits

- Current main-owner login email is authoritative, even if billing email differs.
- Additional contacts do not verify the main owner's email on their behalf.
- Existing native verification for the current owner email is recognized.
- Native owner email edits require new verification and revoke old OTP/proof.
- Five-minute OTP expiry, five failed attempts, persistent request limits and
  resend cooldown; ambiguous sends are not automatically retried.
- Session-bound forms, CSRF protection and private/no-store verification pages.
- Official English and Indonesian addon catalogs; no core/theme files replaced.

Runtime PHP implementation is ionCube encoded. Only the language catalogs
and client template remain readable/customizable. This is a proprietary
free-to-use distribution, not a publication of the implementation source.

Do not enable this and another Herza verification addon gate together. This
package uses the same addon ID as the separate commercial email-only product;
it is not a second independently installable addon.

There is no purchase/renewal checkout in this repository and no online license
activation service is included. WHMCS, ionCube Loader, hosting and mail-provider
services remain separate requirements. See the [user guide](docs/USER-GUIDE.md).

Copyright 2026 Herza, Ltd. All rights reserved except the permissions in LICENSE.md.
