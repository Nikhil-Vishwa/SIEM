# SIEM Features and Functions

## Core Functions

- Collect security logs from endpoints, servers, applications, and network devices.
- Accept logs through file upload, HTTP API, Syslog, or agent-based input.
- Normalize different log formats into one common schema.
- Store events for later search and investigation.
- Index events for fast querying.
- Detect suspicious activity using rules and thresholds.
- Generate alerts when rule conditions match.
- Show events, alerts, and trends in a dashboard.
- Support manual investigation and incident tracking.

## Security Features

- User authentication.
- Role-based access control.
- Audit logging for user and admin actions.
- Encrypted secrets and protected configuration.
- Raw log preservation for forensic review.

## Investigation Features

- Search by time, source, host, user, IP, severity, and tags.
- Filter and sort events quickly.
- Open event details for deeper inspection.
- Link alerts to related events.
- Track cases or incidents manually.

## Detection Features

- Rule-based detection.
- Threshold-based detection.
- Repeated-event detection.
- Severity assignment for alerts.
- Alert suppression and deduplication.

## Dashboard Features

- Recent alerts view.
- Event volume overview.
- Top sources, hosts, users, and rules.
- Basic trend charts.

## Data Features

- Raw event storage.
- Normalized event storage.
- Search index support.
- Tags and metadata support.
- Time-based event records.

## Operational Functions

- Log ingestion pipeline.
- Event parsing and normalization.
- Alert creation and storage.
- Search and retrieval.
- Basic reporting and export.

## How It Works

When the application is running, it continuously does a few things in the background:

1. Receives logs or events from supported sources.
2. Parses and normalizes each incoming event.
3. Saves the raw and normalized data.
4. Indexes the event so it can be searched quickly.
5. Checks the event against detection rules.
6. Creates an alert if a rule matches.
7. Updates dashboards and search results for the user.

In simple terms, the app watches incoming security data, organizes it, stores it, searches it, and raises alerts when something looks suspicious.
