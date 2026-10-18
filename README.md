# Sentinel Genesis Scheme Calculator

## Static two-page application

- `index.html` is the login and user-management hub.
- `dashboard.html` contains only the scheme calculator and financial dashboard. It checks `sessionStorage` for `sentinel_auth === "true"` and redirects unauthenticated visitors to `index.html`.
- `wasmer.toml` serves the repository root as a static site, so `index.html` is the default entry page. No PHP runtime or build process is required.

The login page hardcodes the protected `Admin` account and seeds the `Sanjay` and `Pratyush` secondary accounts into browser `localStorage` on first use. The Admin credentials are not stored in or changed through local storage. **Reset Users** clears every secondary account, leaving only the hardcoded Admin account available. A successful sign-in stores `sentinel_auth = "true"` and `sentinel_username` in `sessionStorage`. Dashboard logout clears session storage and returns to the login page.

**Security warning:** this is client-side convenience, not secure access control. Default passwords, added user passwords, and the master passcode are available in the public JavaScript and browser storage. The session flag can also be changed or bypassed. Do not use this static version to protect confidential information.
