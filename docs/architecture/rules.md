# Detection Rules

This document explains how detection logic works in the SIEM.

## What rules do

Rules inspect normalized events and decide whether they are suspicious enough to create an alert.

## Rule types

### 1. Pattern-based rules
- Match a specific message, source, host, user, or tag.
- Example: a log line contains "failed login".

### 2. Threshold-based rules
- Count repeated events over a time window.
- Example: 10 failed logins from the same user in 5 minutes.

### 3. Repeated-event rules
- Detect the same event happening again and again.
- Example: the same error appears many times from one host.

### 4. Severity-based rules
- Trigger when a field exceeds a severity level.
- Example: any event marked high or critical.

### 5. Suppression rules
- Prevent duplicate alerts.
- Example: only one alert per host per 15 minutes for the same rule.

## Simple rule example

- IF `event_type = login_failure`
- AND `count >= 5 within 10 minutes`
- THEN create alert with severity `high`

## Alert output

When a rule matches, the system should store:
- Rule id
- Event id or event ids
- Alert severity
- Alert status
- Timestamp
- Notes or summary

## Good rule design

- Keep rules easy to read.
- Start with a small number of rules.
- Test each rule with sample logs.
- Avoid noisy rules that trigger too often.
- Document why each rule exists.

## Early rule examples

- Failed login burst
- Multiple invalid password attempts
- Suspicious admin activity
- Repeated application error spike
- New host generating unusual events

## Relation to the worker

The worker should evaluate rules after normalization and storage. The worker can read from the database or queue and create alerts only when conditions are met.
