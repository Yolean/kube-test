# kube-test

A test pod is one with labels:

```yaml
        test-target: your-project
        test-type: readiness
```

That has status `NotReady` whenever an assertion fails.
This means you can see the status of your services using:

```bash
kubectl get pods -l test-type=readiness -w --all-namespaces
```

Add `,test-target=your-project` to `-l` to see only your tests. 

## Docker images

### [kube-test-bash](https://hub.docker.com/r/solsson/kube-test-bash/)

### [kube-test-nodejs](https://hub.docker.com/r/solsson/kube-test-nodejs/)

