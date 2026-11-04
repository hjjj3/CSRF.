# CSRF – Remediation and Fixes

To protect the application against Cross-Site Request Forgery (CSRF), the following security measures should be implemented:

## 1. Anti-CSRF Tokens
Generate a unique and unpredictable token for each user session. Validate the token on every state-changing request, such as `POST /transfer`.

## 2. SameSite Cookies
Configure session cookies with the appropriate SameSite attribute:

- `SameSite=Strict`: Blocks cookies in cross-site requests.
- `SameSite=Lax`: Provides protection against many cross-site request scenarios.

## 3. Origin Validation
Validate the `Origin` header against trusted application domains for sensitive requests.

## 4. Re-Authentication / MFA
Require password confirmation or Multi-Factor Authentication (MFA) before executing sensitive operations.

## Conclusion
Combining CSRF tokens, secure cookie settings, and origin validation provides strong protection against CSRF attacks.
