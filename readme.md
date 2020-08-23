# Current Service version

| Service        | Repository           | Current Version  |
| -------------- | -------------------- | ----------------:|
| participant-api      | api-gateway | v0.7.1 |
| management-api      | api-gateway | v0.7.1 |
| study-service      | study-service | v0.10.0 |
| user-management-service      | user-management-service | v0.12.1 |
| email-client-service      | messaging-service | v0.6.1 |
| message-scheduler      | messaging-service | v0.6.1 |
| messaging-service      | messaging-service | v0.6.1 |
| logging-service      | logging-service | v0.1.0 |
| web-client      | web-client | v0.8.1 |


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
