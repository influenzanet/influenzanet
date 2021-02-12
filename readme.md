# Current Service version

| Service        | Repository           | Current Version  |
| -------------- | -------------------- | ----------------:|
| participant-api      | api-gateway | v0.12.1 |
| management-api      | api-gateway | v0.12.1 |
| study-service      | study-service | v0.13.4 |
| user-management-service      | user-management-service | v0.19.1 |
| email-client-service      | messaging-service | v0.9.1 |
| message-scheduler      | messaging-service | v0.9.1 |
| messaging-service      | messaging-service | v0.9.1 |
| logging-service      | logging-service | v0.1.0 |
| web-client      | web-client | v0.21.6 |


# Influenzanet Issue Collector and Wiki

To submit an issue (bug report, question, suggestion) go to the [issues section](https://github.com/influenzanet/influenzanet/issues).

# Recommended DB indexes:

## Global Infos
Database: 
```<Prefix>global-infos```
Collection: 
```temp-tokens```

- token
- userID + instanceID + purpose
- expiration

## User DB
Database: 
```<Prefix><InstanceID>_users```
Collection: 
```users```

- accountID
- account.accountConfirmedAt + timestamps.createdAt -> useful for clean up task (unverified accounts)

## Study DB
Database: 
```<Prefix><InstanceID>_studyDB```
Collection: 
```<studyKey>_participants```

- participantID
- participantID + studyStatus

---

Database: 
```<Prefix><InstanceID>_studyDB```
Collection: 
```<studyKey>_surveyResponses```

- participantID + key + submittedAt
- participantID
- submittedAt

## Message DB

Database:
```<Prefix><InstanceID>_messageDB```
Collection: 
```outgoing-emails```
- lastSendAttempt + highPrio
