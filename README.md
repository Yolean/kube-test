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

You can use any container, any language, but these include some tools we typically need.

### [kube-test-bash](https://hub.docker.com/r/solsson/kube-test-bash/)

### [kube-test-nodejs](https://hub.docker.com/r/solsson/kube-test-nodejs/)

## Test development

In nodejs tests you'll want to copy tests sources to the container,
then generate a ConfigMap when you're done.

If https://kubernetes.io/docs/tasks/debug-application-cluster/local-debugging/
is too heavyweight, a `kubectl cp` based approach might suffice.

https://superuser.com/questions/181517/how-to-execute-a-command-whenever-a-file-changes

https://stackoverflow.com/questions/1515730/is-there-a-command-like-watch-or-inotifywait-on-the-mac

https://marketplace.visualstudio.com/items?itemName=emeraldwalk.RunOnSave
