# Ode Organizer Alerts
Overview for alerts available for verified Organizer entities to generate when adding or modifying events.

## Alert Structure

The alerts system is designed to track and record various events and actions within the platform. Each alert is represented by the following key columns:

### Columns

| Column Name | Type | Description | Example |
|------------|------|-------------|---------|
| `alertid` | Integer | Unique identifier for the alert | `15` |
| `created_at` | Timestamp | Automatic timestamp of alert creation | `2024-12-09 00:06:55` |
| `organizerid` | Integer | ID of the organizing user's profile | `3` |
| `alert_type` | String | Type of alert being recorded | `"eventAdded"` |
| `alert_metadata` | JSON | Structured metadata specific to the alert type | `{"eventid": 90, "message": "..."}` |

## Event Added Alert (`eventAdded`)

### Metadata Structure

When an event is added to the system, an `eventAdded` alert is generated with the following metadata fields:

| Field | Type | Description | Example |
|-------|------|-------------|---------|
| `eventid` | Integer | Unique identifier of the newly created event | `90` |
| `message` | String | Human-readable description of the event addition | `"Added \"George Balanchine's the Nutcracker\" on Dec, 19, 2024"` |

### Example Alert

```json
{
    "alertid": 15,
    "created_at": "2024-12-09 00:06:55",
    "organizerid": 3,
    "alert_type": "eventAdded",
    "alert_metadata": {
        "eventid": 90,
        "message": "Added \"George Balanchine's the Nutcracker\" on Dec, 19, 2024"
    }
}
```