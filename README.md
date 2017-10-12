# kube-test

A test pod is one with labels

```yaml
        test-target: your-project
        test-type: readiness
```

...that has status `NotReady` whenever an assertion fails.
This means you can see the status of your services using:

```bash
kubectl get pods -l test-type=readiness -w --all-namespaces
```

(add `,test-target=your-project` to `-l` to see only your tests)

Tests typically live in the `default` namespace, rather than that of your project,
so they can serve as examples of accessing your services.

## Docker images

### [kube-test-bash](https://hub.docker.com/r/solsson/kube-test-bash/)

### [kube-test-nodejs](https://hub.docker.com/r/solsson/kube-test-nodejs/)

