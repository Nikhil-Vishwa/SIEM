# Sample Alerts and Cases

This file shows examples of alerts and how they can turn into cases.

## Example alert 1: Failed login burst

- Alert id: A-001
- Rule: Failed login burst
- Severity: high
- Source: auth-service
- Host: server-01
- User: alice
- Reason: 10 failed logins in 5 minutes
- Status: open

### Possible case
- Case title: Investigate repeated failed logins for alice
- Status: open
- Owner: analyst-01
- Notes: check whether the account is under attack or if the password is expired.

## Example alert 2: Application error spike

- Alert id: A-002
- Rule: Application error spike
- Severity: medium
- Source: payment-api
- Host: app-02
- Reason: error count exceeded threshold
- Status: open

### Possible case
- Case title: Review payment API failures
- Status: in progress
- Owner: analyst-02
- Notes: check logs, recent deployments, and dependency failures.

## Example alert 3: Suspicious access denial pattern

- Alert id: A-003
- Rule: Repeated access denied
- Severity: high
- Source: vpn-gateway
- Host: vpn-01
- Reason: repeated invalid access from same IP
- Status: open

### Possible case
- Case title: Investigate possible brute-force attempt
- Status: open
- Owner: analyst-03
- Notes: identify source IP and verify if activity is malicious.

## What an alert should include

- Alert id
- Rule name
- Severity
- Event link
- Time created
- Status
- Notes
- Case link if one exists
