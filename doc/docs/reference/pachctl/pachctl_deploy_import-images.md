## pachctl deploy import-images

Import a tarball (from stdin) containing all of the images in a deployment and push them to a private registry.

### Synopsis


Import a tarball (from stdin) containing all of the images in a deployment and push them to a private registry.

```
pachctl deploy import-images <input-file>
```

### Options inherited from parent commands

```
      --block-cache-size string       Size of pachd's in-memory cache for PFS files. Size is specified in bytes, with allowed SI suffixes (M, K, G, Mi, Ki, Gi, etc).
  -c, --context string                Name of the context to add to the pachyderm config.
      --dash-image string             Image URL for pachyderm dashboard
      --dashboard-only                Only deploy the Pachyderm UI (experimental), without the rest of pachyderm. This is for launching the UI adjacent to an existing Pachyderm cluster. After deployment, run "pachctl port-forward" to connect
      --dry-run                       Don't actually deploy pachyderm to Kubernetes, instead just print the manifest.
      --dynamic-etcd-nodes int        Deploy etcd as a StatefulSet with the given number of pods.  The persistent volumes used by these pods are provisioned dynamically.  Note that StatefulSet is currently a beta kubernetes feature, which might be unavailable in older versions of kubernetes.
      --etcd-cpu-request string       (rarely set) The size of etcd's CPU request, which we give to Kubernetes. Size is in cores (with partial cores allowed and encouraged).
      --etcd-memory-request string    (rarely set) The size of etcd's memory request. Size is in bytes, with SI suffixes (M, K, G, Mi, Ki, Gi, etc).
      --etcd-storage-class string     If set, the name of an existing StorageClass to use for etcd storage. Ignored if --static-etcd-volume is set.
      --expose-object-api             If set, instruct pachd to serve its object/block API on its public port (not safe with auth enabled, do not set in production).
      --image-pull-secret string      A secret in Kubernetes that's needed to pull from your private registry.
      --local-roles                   Use namespace-local roles instead of cluster roles. Ignored if --no-rbac is set.
      --log-level string              The level of log messages to print options are, from least to most verbose: "error", "info", "debug". (default "info")
      --namespace string              Kubernetes namespace to deploy Pachyderm to.
      --new-storage-layer             (feature flag) Do not set, used for testing.
      --no-color                      Turn off colors.
      --no-dashboard                  Don't deploy the Pachyderm UI alongside Pachyderm (experimental).
      --no-expose-docker-socket       Don't expose the Docker socket to worker containers. This limits the privileges of workers which prevents them from automatically setting the container's working dir and user.
      --no-guaranteed                 Don't use guaranteed QoS for etcd and pachd deployments. Turning this on (turning guaranteed QoS off) can lead to more stable local clusters (such as a on Minikube), it should normally be used for production clusters.
      --no-rbac                       Don't deploy RBAC roles for Pachyderm. (for k8s versions prior to 1.8)
  -o, --output string                 Output format. One of: json|yaml (default "json")
      --pachd-cpu-request string      (rarely set) The size of Pachd's CPU request, which we give to Kubernetes. Size is in cores (with partial cores allowed and encouraged).
      --pachd-memory-request string   (rarely set) The size of PachD's memory request in addition to its block cache (set via --block-cache-size). Size is in bytes, with SI suffixes (M, K, G, Mi, Ki, Gi, etc).
      --registry string               The registry to pull images from.
      --shards int                    (rarely set) The maximum number of pachd nodes allowed in the cluster; increasing this number blindly can result in degraded performance. (default 16)
      --static-etcd-volume string     Deploy etcd as a ReplicationController with one pod.  The pod uses the given persistent volume.
      --tls string                    string of the form "<cert path>,<key path>" of the signed TLS certificate and private key that Pachd should use for TLS authentication (enables TLS-encrypted communication with Pachd)
  -v, --verbose                       Output verbose logs
```

