# Dashboard

This document explains what the dashboard should show and why.

## Dashboard purpose

The dashboard gives analysts a quick view of what is happening in the SIEM right now.

## Main dashboard sections

### 1. Recent alerts
- Shows newly created alerts.
- Displays severity, rule name, source, and time.
- Helps analysts triage quickly.

### 2. Event volume overview
- Shows how many events are arriving over time.
- Helps spot spikes or outages.

### 3. Top sources
- Shows which hosts, applications, or devices generate the most logs.
- Helps identify noisy systems and important assets.

### 4. Top users
- Shows which users appear most often in logs.
- Helps spot suspicious or unusual user behavior.

### 5. Top rules
- Shows which rules trigger most often.
- Helps identify noisy or important detections.

### 6. Trend charts
- Shows event counts over time.
- Shows alert trends over time.
- Supports quick visual investigation.

## What the dashboard should support

- Search from the dashboard.
- Open an event detail view.
- Open an alert detail view.
- Link an alert to a case.
- Filter by time range.
- Refresh data periodically.

## What data the dashboard reads

- Normalized events
- Alerts
- Cases
- User and role metadata
- Event counts and rule counts

## Dashboard design goal

The dashboard should be simple, readable, and useful for fast security review on a local laptop.
