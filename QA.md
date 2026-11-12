# Verification record

Verified in the browser on 11 November 2026 using the local HTTP preview.

## Passed

- Preview returned HTTP 200; JavaScript syntax checks passed with `npm run check`.
- Created an anonymous report with title, description, Lighting category, Central Library location, map position, and accessibility flag.
- Submission produced reference **CF-1043**, confirmation, and an automatic follow.
- Opened the report, added a community update, and verified the visible comment.
- Searched CF-1043 in the list, switched to the map, and opened the same report by its pin.
- Confirmed the ordinary student detail view had zero staff management buttons.
- Entered the explicit Demo Staff role; set In progress, High priority, Facilities team, estimated completion, and public explanation.
- Confirmed the public history displayed the changed status, priority, team, estimate, and explanation.
- Refreshed and confirmed report and staff session persistence. Exited the staff role and reopened the report through Following.
- Attempted a link-containing comment; the visible error rejected it.
- Combined category, location, status, urgency, and reported-since filters returned the expected report.
- An incompatible status filter produced a usable empty state.
- Checked responsive overview, report list, map, details, staff dashboard, and staff editor at 390px mobile width. Document and modal scroll widths did not exceed their client widths.
- Checked tablet overview at 768px width and desktop overview at the browser's default width.
- Improved supporting-text contrast and added a persistent accessible name to the mobile report button.
- No browser warning/error logs were reported in the final overview check.

## Scope limits

Manual browser QA covered the main workflow above. It was not a formal WCAG audit or an exhaustive test across browser engines. Photo upload, full-storage and corrupted-storage recovery branches were implemented and reviewed but were not manually exercised with real files or destructive storage manipulation. Real authentication, shared multiuser storage, server moderation, campus delivery, and email/push notifications are not configured.

The browser used for testing contains the extra CF-1043 test report. The delivered source starts a new visitor with the original twelve samples; no test-created data is embedded in the source.
