# Local Runbook

This runbook explains how to operate the SIEM locally on a laptop.

## Startup checklist

- Confirm the repository is cloned.
- Confirm the root folders exist.
- Confirm sample data is available.
- Confirm configuration secrets are not committed.
- Start local services with the compose file when it exists.

## Normal local workflow

1. Start services.
2. Load sample logs.
3. Open the dashboard.
4. Check event ingestion.
5. Check indexing and search.
6. Review alerts.
7. Open or create cases.

## Basic troubleshooting

### If logs are not showing up
- Check the API service.
- Confirm the raw storage folder exists.
- Confirm the sample log format is valid.

### If search is empty
- Check whether the worker normalized the event.
- Check whether the search index is running.
- Check whether the event was indexed successfully.

### If alerts are not created
- Check the rule engine.
- Check rule conditions.
- Check whether the normalized event matches the rule.

### If the dashboard is stale
- Refresh the page.
- Check event ingestion.
- Check whether the UI is reading the latest data.

## Recovery notes

- Preserve raw logs.
- Re-run sample imports if needed.
- Rebuild the search index if data is missing.
- Review audit logs for access issues.

## Local safety notes

- Keep the project on one machine during the early build.
- Use free and open-source services only.
- Avoid storing secrets directly in the repository.
