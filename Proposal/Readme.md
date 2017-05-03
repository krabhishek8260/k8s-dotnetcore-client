# Kubernetes dotnet core client 

Dotnet core client for the [kubernetes](http://kubernetes.io/) API.

## v0.1 requirements/features
- Auto generated from swagger using autorest
- Support configuring client through kube config file
- Support secure connections to api server
- Support client-cert and token based(Basic and Bearer) auths
- Support all basic APIs


## Example

List all pods:

```csharp
var kubeClientConfig = new ClientConfiguration(new FileInfo(@"kubeconfig"));
var kubernetesClient = new Kubernetes(kubeClientConfig);
var pods = kubernetesClient.ListCoreV1NamespacedPodAsync("default").Result;
foreach (var pod in pods.Items)
{
	Console.WriteLine(JsonConvert.SerializeObject(pod));
}
```

### Code of Conduct

Participation in the Kubernetes community is governed by the [CNCF Code of Conduct](https://github.com/cncf/foundation/blob/master/code-of-conduct.md).

## Kubernetes Incubator

This is a [Kubernetes Incubator project](https://github.com/kubernetes/community/blob/master/incubator.md). 

* [SIG: sig-api-machinery](https://github.com/kubernetes/community/tree/master/sig-api-machinery)

## Timeline

- v0.1 Release: End of May

## Notes

The client is dependent on OpenSSL for cert generation and is only suppported on Linux as of now.

## Community
Champion: brendandburns
