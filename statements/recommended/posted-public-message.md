# Posted public message

## Description

A participant has posted a public message in the virtual classroom chat.

## Example

```json
{
   "actor": {
      "account": {
         "name": "john",
         "homePage": "http://gaiax-virtualclassroom.org"
      }
   },
   "verb": {
      "id": "https://w3id.org/xapi/acrossx/verbs/posted"
   },
   "object": {
      "id": "http://gaiax.org/xapi/activities/f3757ec4-e427-4e3e-a934-fbccdd440a32",
      "definition": {
         "type": "https://w3id.org/xapi/acrossx/activities/message",
         "name": {
            "en": "Message of John #23"
         }
      }
   },
   "context": {
      "registration": "4eb0e063-669b-479a-86b3-f9be9ac88a1d",
      "contextActivities": {
         "parent": [
            {
               "id": "http://gaiax.org/xapi/activities/e59490e1-ddf2-4c43-bfdc-14e274abc106",
               "definition": {
                  "type": "https://w3id.org/xapi/virtual-classroom/activity-types/virtual-classroom"
               }
            }
         ],
         "category": [
            {
               "id": "https://w3id.org/xapi/virtual-classroom",
               "definition": {
                  "type": "http://adlnet.gov/expapi/activities/profile"
               }
            }
         ]
      },
      "extensions": {
         "https://w3id.org/xapi/cmi5/context/extensions/sessionid": "c7b6f0a9-482c-4c03-acc1-548289126963"
      }
   },
   "timestamp": "2016-06-09T15:34:26.887Z"
}
```

## Determining properties

| Property  | Value         |
|----------------|-----------------|
| verb.id | Must be `https://w3id.org/xapi/acrossx/verbs/posted` |
| object.type | Must be `https://w3id.org/xapi/acrossx/activities/message` |

## Rules

- `context.registration`: INCLUDED, must be the same for all the statements of a planned session, even when the virtual classroom is relaunched for technical reasons.
- `context.contextActivities.parent`: MUST be the virtual classroom activity.
- `context.contextActivities.category`: MUST contain an activity with the `https://w3id.org/xapi/virtual-classroom` id.
- `context.extensions.https://w3id.org/xapi/cmi5/context/extensions/sessionid`: INCLUDED, UUID format, must be the same for all the statements from `initialized` to `terminated` (i.e. technical session).
- `timestamp`: INCLUDED.



