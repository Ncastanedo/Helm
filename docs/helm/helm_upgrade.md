## helm upgrade

upgrade a release

### Synopsis



This command upgrades a release to a new version of a chart.

The upgrade arguments must be a release and chart. The chart
argument can be either: a chart reference('stable/mariadb'), a path to a chart directory,
a packaged chart, or a fully qualified URL. For chart references, the latest
version will be specified unless the '--version' flag is set.

To override values in a chart, use either the '--values' flag and pass in a file
or use the '--set' flag and pass configuration from the command line, to force string
values, use '--set-string'.

You can specify the '--values'/'-f' flag multiple times. The priority will be given to the
last (right-most) file specified. For example, if both myvalues.yaml and override.yaml
contained a key called 'Test', the value set in override.yaml would take precedence:

	$ helm upgrade -f myvalues.yaml -f override.yaml redis ./redis

You can specify the '--set' flag multiple times. The priority will be given to the
last (right-most) set specified. For example, if both 'bar' and 'newbar' values are
set for a key called 'foo', the 'newbar' value would take precedence:

	$ helm upgrade --set foo=bar --set foo=newbar redis ./redis


```
helm upgrade [RELEASE] [CHART]
```

### Options

```
      --ca-file string           verify certificates of HTTPS-enabled servers using this CA bundle
      --cert-file string         identify HTTPS client using this SSL certificate file
      --description string       specify the description to use for the upgrade, rather than the default
      --devel                    use development versions, too. Equivalent to version '>0.0.0-0'. If --version is set, this is ignored.
      --dry-run                  simulate an upgrade
      --force                    force resource update through delete/recreate if needed
  -i, --install                  if a release by this name doesn't already exist, run an install
      --key-file string          identify HTTPS client using this SSL key file
      --keyring string           path to the keyring that contains public signing keys (default "~/.gnupg/pubring.gpg")
      --namespace string         namespace to install the release into (only used if --install is set). Defaults to the current kube config namespace
      --no-hooks                 disable pre/post upgrade hooks
      --password string          chart repository password where to locate the requested chart
      --recreate-pods            performs pods restart for the resource if applicable
      --repo string              chart repository url where to locate the requested chart
      --reset-values             when upgrading, reset the values to the ones built into the chart
      --reuse-values             when upgrading, reuse the last release's values and merge in any overrides from the command line via --set and -f. If '--reset-values' is specified, this is ignored.
      --set stringArray          set values on the command line (can specify multiple or separate values with commas: key1=val1,key2=val2)
      --set-string stringArray   set STRING values on the command line (can specify multiple or separate values with commas: key1=val1,key2=val2)
      --timeout int              time in seconds to wait for any individual Kubernetes operation (like Jobs for hooks) (default 300)
      --tls                      enable TLS for request
      --tls-ca-cert string       path to TLS CA certificate file (default "$HELM_HOME/ca.pem")
      --tls-cert string          path to TLS certificate file (default "$HELM_HOME/cert.pem")
      --tls-key string           path to TLS key file (default "$HELM_HOME/key.pem")
      --tls-verify               enable TLS for request and verify remote
      --username string          chart repository username where to locate the requested chart
  -f, --values valueFiles        specify values in a YAML file or a URL(can specify multiple) (default [])
      --verify                   verify the provenance of the chart before upgrading
      --version string           specify the exact chart version to use. If this is not specified, the latest version is used
      --wait                     if set, will wait until all Pods, PVCs, Services, and minimum number of Pods of a Deployment are in a ready state before marking the release as successful. It will wait for as long as --timeout
```

### Options inherited from parent commands

```
      --debug                           enable verbose output
      --home string                     location of your Helm config. Overrides $HELM_HOME (default "~/.helm")
      --host string                     address of Tiller. Overrides $HELM_HOST
      --kube-context string             name of the kubeconfig context to use
      --kubeconfig string               absolute path to the kubeconfig file to use
      --tiller-connection-timeout int   the duration (in seconds) Helm will wait to establish a connection to tiller (default 300)
      --tiller-namespace string         namespace of Tiller (default "kube-system")
```

### SEE ALSO
* [helm](helm.md)	 - The Helm package manager for Kubernetes.

###### Auto generated by spf13/cobra on 17-Jun-2018