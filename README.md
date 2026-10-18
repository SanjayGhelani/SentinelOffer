# Sentinel Genesis Offer

## Wasmer Static Hosting

This project is a single-file static web application. Set the Wasmer Static Site root to the repository root and deploy `wasmer.toml`; `index.html` is served as the application entry point. No PHP runtime, build step, or server-side authentication service is required.

The login screen, account editor, and calculator are implemented in `index.html`. The initial `Admin`, `Sanjay`, and `Pratyush` accounts and added users are stored as plaintext in browser `localStorage`. The master passcode is embedded in the same public file. User changes are local to the browser/device that made them and do not synchronize to other visitors.

**Security warning:** this client-side login is a visual convenience only and must not protect sensitive information. Anyone can view the credentials and master passcode in the downloaded page source, edit local storage, or bypass the JavaScript check. Do not deploy this version for confidential, regulated, or otherwise restricted data. Use server-side authentication to enforce access control.

Users can be reset to the three built-in accounts with the master passcode from the **Reset Users** tab. This clears users added to that browser only.
