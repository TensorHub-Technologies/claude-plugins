---
description: Sets THriveX Live up for an app - languages, whether the Guide may click and delete, the sites it runs on, the help content it reads - and checks it is ready. Use when asked to set up, configure, or put THriveX Live on an app or website, or to check whether Live is ready for a launch.
argument-hint: "[app or site]"
---

# Set THriveX Live up for an app

Walk the person through setting Live up for `$ARGUMENTS` (an app or site, if given). Change nothing without their
yes.

## 1. Where things stand

`get_settings_summary`: assistant name, languages, default language, clicks (`allow_actions`) and deleting
(`allow_deletes`), allowed sites, models. Summarise it in a few lines.

## 2. Decide together

Ask only what isn't already clear:

- **Languages** the app's users speak (codes such as `en-IN`, `hi-IN`, `ta-IN`) and the default.
- **Clicks**: may the Guide click and fill forms for users who allow it? Users still type their own passwords,
  OTPs and payment details, and the Guide asks before outward or final actions such as a final Submit.
- **Deleting**: may it delete things, with the user's yes each time? Off unless they want it.
- **Sites**: the `https://` addresses where the widget will run.
- **Assistant name**, if they want their own.

Then state exactly what will change and, on their yes, make one `update_settings_basic` call with only the
changed values.

## 3. Help content

Ask for the app's public help centre. On their yes, `add_knowledge_url` with it (`sitemap=true` for a sitemap).
For anything not yet written, offer the `help-writer` skill.

## 4. Put it on the app

The connector can't hand out the embed code. The person copies the script tag from the THriveX Live console,
**Settings › Install › Embed snippet**, and adds it to every page of the app (before `</body>`). For staff using
other websites, point to the Chrome extension (the `it-rollout` skill).

## 5. Readiness check

Ask for three questions real users would ask. For each, `search_knowledge` and say whether the help content
answers it. Report: settings as they now stand, help content added, the readiness result, and what is left (the
script tag, gaps to write up).

If a change is refused because the connection only reads, the person disconnects THriveX Live in Claude and
connects again; only owners and admins can change settings, and Starter reads only.
