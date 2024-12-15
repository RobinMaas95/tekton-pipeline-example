# tekton-pipeline-example

## How to use:

- Follow [tekton example](https://tekton.dev/docs/installation/local-installation/) to install tekton into your (local) cluster
- Install [tkn cli tool](https://tekton.dev/docs/cli/)
- Apply files in the repo
- Forward Port (`kubectl port-forward service/el-hello-listener 8080`)
- Call endpoint via curl:
  ``` bash
    curl -v \
          -H 'content-Type: application/json' \
          -d '{"username": "Test_User"}' \
          http://localhost:8080
  ```
- List pipeline runs (`tkn pipelineruns list`)
- Check logs of latest pipeline (`tkn pipelinerun logs hello-goodbye-run-...`)

## Example
The example curl from above gives the follwoing log output:
```
tkn pipelinerun logs hello-goodbye-run-6tc65
[hello : echo] Hello World

[goodbye : goodbye] Transformed input test-user!
```

