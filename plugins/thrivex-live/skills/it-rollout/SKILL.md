---
description: Helps IT roll THriveX Live's Chrome extension out to everyone in a company on managed Chrome and Edge - which file to use for Windows Group Policy or Intune, macOS (Jamf, Kandji, Intune) or the Google Admin console, and how to limit the sites it works on. Use when asked to install or deploy the THriveX Live extension for all staff, or about its IT policy.
argument-hint: "[windows|mac|google]"
---

# Roll the THriveX Live extension out to everyone

Help IT install the THriveX Live Chrome extension on every managed Chrome and Edge, already connected to the
company's account, so nobody has to open a link or set anything up.

## The files come from the console

The connector doesn't hand out rollout files. An owner or admin downloads them from the THriveX Live console:
**Settings › Chrome extension › Roll out to everyone (for IT)**. Each file already carries the company's key.
The extension is force-installed from the Chrome Web Store (id `cadamlfmpfkhkkhghedkncneaklemmej`).

Before downloading, decide the optional site lists there:

- **Only these sites**: one per line (`*.yourcompany.com`). When set, the Guide works only on these.
- **Never on these sites**: for example an HR or payroll site.

## Pick the file for `$ARGUMENTS` (ask if not given)

| Fleet | File | How |
|---|---|---|
| Windows | `thrivex-live-rollout.reg` | Import it, push it with Group Policy, or add the same settings in Intune |
| macOS | `thrivex-live-rollout.mobileconfig` | Upload it to Jamf, Kandji or Intune |
| ChromeOS / Google-managed Chrome | `thrivex-live-policy.json` | Google Admin console: add the extension by id, set it to Force install, paste this as its policy |

## Check

After the policy reaches a test machine: `chrome://policy` (or `edge://policy`) shows the extension's policy,
`chrome://extensions` shows THriveX Live installed and not removable, and opening the extension shows the company
already connected. Suggest a pilot group first, then everyone.

Optionally call `get_settings_summary` to confirm `extension_enabled` is on for the company; if it is off, an
admin turns it on under Settings › Chrome extension.

Never ask for or handle passwords, keys or admin credentials: IT applies the policy with their own tools.
