# Data Flow

This document explains how data moves through the SIEM from the moment a log arrives until it is stored, indexed, detected, and shown in the UI.

## Step-by-step flow

1. A source generates a log.
- The source can be an endpoint, server, application, network device, file upload, Syslog sender, HTTP client, or agent.

2. The ingestion layer receives the log.
- The API validates the payload.
- The API records the raw message exactly as received.
- The API assigns a unique id and timestamp metadata.

3. Raw storage keeps the original event.
- The raw payload is written to disk in `data/raw`.
- The original event is preserved for forensic use.
- The raw record should not be overwritten.

4. A worker normalizes the event.
- The worker reads the raw payload.
- It extracts a common event schema.
- It maps different source formats into a single structure.

5. The normalized event is stored.
- The normalized record is saved to the database.
- The system keeps fields such as source, host, user, severity, tags, and message.

6. The event is indexed for search.
- The normalized event is sent to the search index.
- Search is used for filtering, sorting, and fast event lookup.

7. Detection rules evaluate the event.
- The rule engine checks the event against rule conditions.
- Thresholds, repeats, and suspicious patterns can trigger an alert.

8. Alerts are created.
- If a rule matches, an alert is stored.
- The alert is linked to the original event(s).
- The alert can later be triaged or acknowledged.

9. The UI displays the results.
- The dashboard shows alerts and trends.
- Analysts search events, open event details, and investigate suspicious activity.

10. Cases and exports are created.
- Analysts can create a case from an alert.
- Reports or exports can be generated for review or compliance.

## Components involved

- Ingestion/API
- Raw storage
- Worker / normalizer
- Event database
- Search index
- Rule engine
- Alerts store
- Web UI
- Case management
- Export/reporting

## Why this flow matters

This flow keeps the system simple and local-first while still supporting the main SIEM work: collect, normalize, index, detect, alert, investigate, and report.
