# Answered poll question

## Description

A participant answered to a poll question.

## Example

```json
{
   "actor": {
      "objectType": "Agent",
      "account": {
         "name": "john",
         "homePage": "http://gaiax-virtualclassroom.org"
      }
   },
   "verb": {
      "id": "http://adlnet.gov/expapi/verbs/answered"
   },
   "object": {
      "id": "http://gaiax.org/xapi/activities/f3757ec4-e427-4e3e-a934-fbccdd440a32",
      "description": {
            "en-US": "Which e-Learning standard do you know?"
        },
        "type": "http://adlnet.gov/expapi/activities/cmi.interaction",
        "interactionType": "choice",
        "choices": [
            {
                "id": "scorm", 
                "description": {
                    "en-US": "SCORM"
                }
            },
            {
                "id": "xapi", 
                "description": {
                    "en-US": "xAPI"
                }
            },
            {
                "id": "lti", 
                "description": {
                    "en-US": "LTI"
                }
            }
        ]
   },
   "result": {
        "response": "scorm[,]xapi"
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
| verb.id | Must be `http://adlnet.gov/expapi/verbs/answered` |
| object.type | Must be `http://adlnet.gov/expapi/activities/cmi.interaction` |

## Rules

- `object.definition`: CMI interaction, including a content type set to `http://adlnet.gov/expapi/activities/cmi.interaction` and other related properties as described in the xAPI specification.
- `result.response`: INCLUDED, must be consistent with the `correctResponsesPattern` format in case of multiple answers (`[,]` is used as a separator).
- `context.registration`: INCLUDED, must be the same for all the statements of a planned session, even when the virtual classroom is relaunched for technical reasons.
- `context.contextActivities.parent`: MUST be the virtual classroom activity.
- `context.contextActivities.category`: MUST contain an activity with the `https://w3id.org/xapi/virtual-classroom` id.
- `context.extensions.https://w3id.org/xapi/cmi5/context/extensions/sessionid`: INCLUDED, UUID format, must be the same for all the statements from `initialized` to `terminated` (i.e. technical session).
- `timestamp`: INCLUDED.
