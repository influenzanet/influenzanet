# Current Service version

| Service        | Repository           | Current Version  |
| -------------- | -------------------- | ----------------:|
| participant-api      | api-gateway | v0.6.0 |
| management-api      | api-gateway | v0.6.0 |
| study-service      | study-service | v0.9.0 |
| user-management-service      | user-management-service | v0.10.0 |
| email-client-service      | messaging-service | v0.6.0 |
| message-scheduler      | messaging-service | v0.6.0 |
| messaging-service      | messaging-service | v0.6.0 |
| web-client      | web-client | v0.4.1 |


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
