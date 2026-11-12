# CampusFix

A responsive, dependency-free campus issue reporting demo. Built with HTML, CSS, and JavaScript. No API keys, build tools, or package installation required.

## Run locally

Install Node.js if needed, open a terminal in this folder, and run:

```sh
npm start
```

Open **http://127.0.0.1:4173**. Use the same URL and port each time: browser storage is specific to an origin. Run `npm run check` to check JavaScript syntax. `PORT` can override the preview port. The preview server binds to loopback only and is intended for local use.

## Deploy later

The complete website is in **dist/**. Upload the contents of that folder to any static web host; `index.html` must be at the site's root. There is no build command. For a repository-based host, select `dist` as the publish/output directory. Hash navigation (`#reports`, `#map`, `#following`, `#staff`) works without server rewrite rules. Files use relative paths so subdirectory hosting also works. The Node preview server is not needed for deployment.

Deploying the demo does not create a shared database or secure staff login. Each visitor receives an independent local demo. Hosting on a new origin starts with fresh sample data.

## What works

- Twelve realistic fictional sample reports with all four statuses, seven categories, six buildings, urgency, accessibility and safety flags.
- Validated report submission, optional JPG/PNG/WebP photo up to 1 MB, anonymity or public display name, map pin and unique browser-local reference.
- Interactive sample campus layout: clickable report pins; new pins can be positioned by mouse, arrow keys, or numeric coordinates. No map API or location tracking.
- Search by title, description, building, or reference; filters by category, building, date, urgency, and status in list, map, following, and staff views.
- Following reports; public update history; anonymous or named comments. Basic link, repeated-character, duplicate-comment and profanity checks, plus a 15-second comment cooldown.
- Separate **Staff workspace** with an explicit **Enter as Demo Staff** action. Change status, priority, category, team and estimate with a required public update. Logout removes staff controls. The demo role survives refresh in the same tab session.
- Counts by status, category, building and urgency; daily incoming-report trend for the last seven days.
- Reports, photos, follows, comments, history, and anonymity preference persist in localStorage. The sample-data reset requires an explicit second action. Storage failures show a useful error and do not claim the report was saved.
- Semantic labels, keyboard controls, native modal focus handling, visible focus, live status/error messages, skip link, reduced-motion support, responsive layouts, and text/symbol indicators alongside status colors.

## Demo boundaries and production setup

This is a hackathon demo. No backend, credential, external API, telemetry, or campus integration is configured. It does not contact staff or emergency services. Photos are saved as data URLs in localStorage, which has limited capacity. A full or blocked storage area produces an error. Use only demo information.

The Demo Staff role is a UI demonstration, **not a security boundary**. Any visitor can enter it and edit their own local sample data. No passwords are embedded. Ordinary student views do not show management controls until the demo role is explicitly enabled.

Before handling real reports:

1. Add a server-side API and shared database for reports, comments, follow relationships, status history, reference allocation, and staff assignments.
2. Add real student/staff sign-in and enforce staff permissions on **every write endpoint**. A client-side role flag must never authorize real staff actions.
3. Store photos in private object storage; validate file signatures, resize and strip metadata, scan uploads, enforce access rules and retention limits.
4. Apply server-side input validation, content moderation, rate limiting, abuse reporting and audit logging. Current client checks are basic and bypassable.
5. Add email/push subscriptions if desired. Currently following only collects reports in the Following page; no notifications leave the browser.
6. Replace fictional buildings/coordinates in `dist/app.js` with your campus layout. The included map needs no configuration. If using a commercial map provider later, configure its allowed origins and follow its key restrictions; private credentials belong on the server.
7. Define campus privacy, safety escalation, retention and response policies and make them available to users.

## Hackathon walkthrough

1. Select **Report an issue**; fill in the title, description, category and building, choose urgency, move the pin, and optionally flag accessibility or safety.
2. Submit; note the reference and open the report.
3. Add a community update. Close the dialog and search the reference in All reports; switch to Campus map and open its pin.
4. Open Staff workspace, enter the explicit Demo Staff role, search the reference, select it, and change the status/team/estimate with a public explanation.
5. Exit Demo Staff, open Following, and inspect the report history. Refresh to demonstrate persistence.

## Files

- `dist/index.html`: application shell
- `dist/styles.css`: responsive styling and accessibility states
- `dist/app.js`: sample data and all application behavior
- `server.mjs`: local static preview server
- `QA.md`: verification results and limits

No third-party runtime assets or fonts are loaded.
