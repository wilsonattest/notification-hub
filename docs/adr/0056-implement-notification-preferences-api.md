# [ADR-0056] Implement Notification Preferences API

## Metadata

| Field | Value |
|-------|-------|
| Date | 2026-01-12 |
| Status | Proposed |
| Deciders | Alex Rivera |

## Context

Users currently have limited control over their notification settings. The existing system only allows enabling or disabling all notifications at the account level. This has led to:

- High unsubscribe rates due to notification fatigue
- Support tickets requesting granular control
- Compliance concerns with GDPR and CCPA requirements for user consent
- Inability to respect user preferences across different notification channels (email, push, SMS)

Product research indicates that 73% of users who churned cited "too many notifications" as a contributing factor.

## Decision

We will implement a comprehensive Notification Preferences API that allows users to:

1. **Channel Preferences** - Enable/disable notifications per channel (email, push, SMS, in-app)
2. **Category Preferences** - Subscribe/unsubscribe from specific notification categories
3. **Frequency Controls** - Set digest preferences (immediate, daily, weekly)
4. **Quiet Hours** - Define time windows when notifications should be held
5. **Priority Override** - Allow critical notifications to bypass quiet hours

The API will follow RESTful conventions:
- `GET /users/{id}/notification-preferences`
- `PATCH /users/{id}/notification-preferences`
- `GET /notification-categories` (list available categories)

## Consequences

### Positive

- Improved user satisfaction and reduced churn
- GDPR/CCPA compliance for notification consent
- Reduced support ticket volume
- Foundation for smart notification delivery optimization
- Better email deliverability (fewer spam reports)

### Negative

- Increased complexity in notification delivery pipeline
- Need to backfill preferences for existing users
- Additional database storage for preference records
- More complex testing matrix for notification scenarios

### Neutral

- Requires coordination with mobile team for SDK updates
- Marketing team will need to update campaign workflows
- Documentation needed for third-party integrators
