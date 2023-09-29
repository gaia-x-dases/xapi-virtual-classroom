# Started camera

## Description

A user has started the camera. The action has been done by the participant itself or by another participant with moderation rights on the virtual classroom cameras. 

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
      "id": "http://activitystrea.ms/start"
   },
   "object": {
      "id": "http://gaiax.org/xapi/activities/c9f4c663-ea5d-48f7-ac6c-4d3534562eed",
      "definition": {
         "type": "https://w3id.org/xapi/virtual-classroom/activity-types/camera",
         "name": {
            "en": "John's camera"
         }
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
         ], 
         "parent": [
            {
               "id": "http://gaiax.org/xapi/activities/e59490e1-ddf2-4c43-bfdc-14e274abc106",
               "definition": {
                  "type": "https://w3id.org/xapi/virtual-classroom/activity-types/camera",
                  "name": {
                     "en": "xAPI 101"
                  },
               },
            },
         ],
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
| `$.verb.id` | Must be `http://activitystrea.ms/start` |
| `$.object.definition.type` | Must be `https://w3id.org/xapi/virtual-classroom/activity-types/camera` |


## Rules

- `$.context.registration`: INCLUDED, must be the same for all the statements of a planned session, even when the virtual classroom is relaunched for technical reasons.
- `$.context.contextActivities.category`: INCLUDED, MUST contain an activity with the `https://w3id.org/xapi/virtual-classroom` id.
- `$.context.extensions.["https://w3id.org/xapi/cmi5/context/extensions/sessionid"]`: INCLUDED, UUID format, must be the same for all the statements from `initialized` to `terminated` (i.e. technical session).
- `$.timestamp`: INCLUDED.
