
Code an API in python to allow users to call different ML models. For the first iteration, we want to be able to:

* create organizations
* add and remove models from organizations
* invoke the models 

The models will be hosted in a separate service, which is currently being built. The team building the models service is providing you with a mock service that can run while developing. It can be reached at the following endpoint: `https://app.staging.baseten.co/applications/Vqmogn0/worklets/VBnodk0.` The models team provided this documentation:

# Authentication

In the HTTP headers:
`Authorization: Api-Key IR5hVxK1.FlYV3hmIazD7FGvXPacQnN38wgw7CSSE`

# Invoke a model

HTTP POST `/invoke`

# JSON body input:

```json
{
  "worklet_input": {
    "model_id": string,
    "input": [int]
  }
}
```

# JSON output:
{
  "worklet_output": [int],
  "success": boolean,
  "latency_ms": string,
  "error_log": string
}

Two calls to a model with the same inputs will produce the same output if there are no errors.

We also want to provide metrics to our end user. The API should include one endpoint to return the history of model invocation and one endpoint to return number of successes and failures for each model

Example curl request:
```sh
curl -X POST \
  https://app.staging.baseten.co/applications/Vqmogn0/worklets/VBnodk0/invoke \
  -H 'Authorization: Api-Key IR5hVxK1.FlYV3hmIazD7FGvXPacQnN38wgw7CSSE' \
  -H 'Content-Type: application/json' \
  -d '{"worklet_input": {"model_id": "0", "input": [1,10,2,20]}}'
```