# My First n8n Workflow

This is my very first n8n workflow! 🎉  

**What it does:**  
- Uses a **Manual Trigger** — run it by clicking “Execute workflow” in n8n.  
- Generates a **random number between 0–99** and stores it in the field `message`.  
- Shows how to use **expressions** in n8n for dynamic values.

---

## Workflow JSON

```json
{
  "name": "My workflow",
  "nodes": [
    {
      "parameters": {},
      "type": "n8n-nodes-base.manualTrigger",
      "typeVersion": 1,
      "position": [0, 0],
      "id": "d3598dcc-2b76-4c76-9e6f-404107619857",
      "name": "When clicking ‘Execute workflow’"
    },
    {
      "parameters": {
        "assignments": {
          "assignments": [
            {
              "id": "1a566165-b1d8-4a2a-a2f6-51dcdf9a2731",
              "name": "message",
              "value": "={{ Math.floor(Math.random() * 100) }}",
              "type": "string"
            }
          ]
        },
        "options": {}
      },
      "type": "n8n-nodes-base.set",
      "typeVersion": 3.4,
      "position": [208, 0],
      "id": "d8e105d2-6803-4e63-945b-31dd10922476",
      "name": "Edit Fields"
    }
  ],
  "pinData": {},
  "connections": {
    "When clicking ‘Execute workflow’": {
      "main": [
        [
          {
            "node": "Edit Fields",
            "type": "main",
            "index": 0
          }
        ]
      ]
    },
    "Edit Fields": {
      "main": [[]]
    }
  },
  "active": false,
  "settings": {
    "executionOrder": "v1",
    "binaryMode": "separate",
    "availableInMCP": false
  },
  "versionId": "d584e622-0ff4-4b4d-8d57-2d824ba28a7d",
  "meta": {
    "templateCredsSetupCompleted": true,
    "instanceId": "73f4d7923d502418e60c4bbeb4f19d60034326ab4b83732a2d355bacabcc3974"
  },
  "id": "Si73zqU2eiOVcIe8",
  "tags": []
}
