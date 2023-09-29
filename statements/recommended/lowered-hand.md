# Lowered hand

## Description

A user has lowered the hand to stop asking for speaking/taking part to the discussion in the virtual classroom.

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
      "id": "https://w3id.org/xapi/virtual-classroom/verbs/unreacted"
   },
   "object": {
      "id": "http://gaiax.org/xapi/activities/e59490e1-ddf2-4c43-bfdc-14e274abc106",
      "definition": {
         "type": "https://w3id.org/xapi/virtual-classroom/activity-types/virtual-classroom",
         "name": {
            "en": "xAPI 101"
         }
      }
   },   
   "result": {
      "extensions": {
         "https://w3id.org/xapi/virtual-classroom/extensions/emoji": "U+1F590"
      }
   },
   "context": {
      "registration": "4eb0e063-669b-479a-86b3-f9be9ac88a1d",
      "contextActivities": {
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

| Property | Value |
|---|---|
| `$.verb.id` | MUST be `https://w3id.org/xapi/dod-isd/verbs/unreacted` |
| `$.object.definition.type` | MUST be `https://w3id.org/xapi/virtual-classroom/activity-types/virtual-classroom` |

## Rules

- `$.context.registration`: INCLUDED, MUST be the same for all the statements of a planned session, even when the virtual classroom is relaunched for technical reasons.
- `$.context.contextActivities.category`: INCLUDED, MUST contain an activity with the `https://w3id.org/xapi/virtual-classroom` id.
- `$.context.extensions.["https://w3id.org/xapi/cmi5/context/extensions/sessionid"]`: INCLUDED, UUID format, MUST be the same for all the statements from `initialized` to `terminated` (i.e. technical session).
- `$.result.extensions.["https://w3id.org/xapi/virtual-classroom/extensions/emoji"]`: INCLUDED, Unicode, MUST be the unicode value for the 🖐️ (`hand raised`) emoji .
- `$.timestamp`: INCLUDED.
