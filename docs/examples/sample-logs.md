# Sample Logs

This file contains example payloads that can be used for testing ingestion, normalization, search, and detection.

## Example 1: Failed login

```json
{
  "timestamp": "2026-06-03T10:15:00Z",
  "source": "auth-service",
  "event_type": "login_failure",
  "severity": "medium",
  "hostname": "server-01",
  "username": "alice",
  "ip_address": "192.168.1.20",
  "message": "Failed login for user alice",
  "tags": ["auth", "security"]
}
```

## Example 2: Successful login

```json
{
  "timestamp": "2026-06-03T10:18:00Z",
  "source": "auth-service",
  "event_type": "login_success",
  "severity": "low",
  "hostname": "server-01",
  "username": "alice",
  "ip_address": "192.168.1.20",
  "message": "User alice logged in successfully",
  "tags": ["auth"]
}
```

## Example 3: Application error

```json
{
  "timestamp": "2026-06-03T10:20:00Z",
  "source": "payment-api",
  "event_type": "error",
  "severity": "high",
  "hostname": "app-02",
  "username": "system",
  "ip_address": "10.0.0.15",
  "message": "Unhandled exception in payment processing",
  "tags": ["application", "error"]
}
```

## Example 4: Repeated invalid access

```json
{
  "timestamp": "2026-06-03T10:25:00Z",
  "source": "vpn-gateway",
  "event_type": "access_denied",
  "severity": "high",
  "hostname": "vpn-01",
  "username": "unknown",
  "ip_address": "203.0.113.55",
  "message": "Multiple invalid access attempts detected",
  "tags": ["vpn", "intrusion"]
}
```

## How to use these samples

- Ingest them through the API.
- Check that they are normalized correctly.
- Verify they appear in search.
- Use them to test rules and alerts.
- Use them to confirm the dashboard updates.
