# Compatibility — Free Edition 1.0.0

| Requirement | Supported target / evidence boundary |
| --- | --- |
| WHMCS | 8.13.7 native clone qualification; Twenty-One functional browser acceptance inherited from the parent 1.0.0 implementation |
| PHP | Encoded targets 8.1, 8.2 and 8.3; validate WHMCS and extension requirements for your exact PHP version |
| ionCube Loader | Declared minimum 15.0; encoded laboratory tests use Loader 15.5. Not every intervening Loader version is independently tested |
| Database | MySQL/MariaDB with InnoDB and dedicated transactional PDO connections |
| Email | Working supported native WHMCS mail configuration, authorized sender/domain and access to the current owner mailbox |
| Languages | English and Indonesian through official addon catalogs; other language selections fall back to English |

The Free Edition changes product/admin labels and the version label from the
qualified parent; verification logic is unchanged. Its actual encoded files
receive fresh isolated PHP/database and native lifecycle/identity/template
checks. A new Free Edition browser or real-email pilot has not been performed.
Parent browser acceptance covered required verification, actual SMTP OTP
success, verified logout/login and free checkout navigation.

Do not infer qualification for WHMCS 8.13.1, WHMCS 9, PHP 8.4+, Six, Hostiko,
other themes, paid gateways, provisioning, renewal, raw UpgradeProduct or
arbitrary API/mobile/admin purchase integrations. Internal Herza deployment
evidence belongs to a separate product and does not expand this matrix.

Recognized native mail interfaces include PHP Mail, SMTP, SendGrid, Mailgun,
SparkPost and Microsoft. Validate actual account authentication, sender approval,
receipt and web-runtime behavior for your chosen provider; interface recognition
is not a claim that every provider account has been tested.

Test account switching, invitations, session expiry, accessibility/mobile layout
and reverse-proxy/CDN cache behavior on your own deployment. First Client ID is
an inclusive lower bound, not a single-client allowlist.
