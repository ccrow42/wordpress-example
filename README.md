# Wordpress example

I'm running this on a single RKE2 node that uses the local path provisioner.

You may want to edit the service configuration in the wordpress.yaml file to change to a load balancer. I am using ingresses for this configuration with let's encrypt.

You will need to install the MariaDB operator for the database manifests to work.

```bash
helm repo add mariadb-operator https://helm.mariadb.com/mariadb-operator
helm install mariadb-operator-crds mariadb-operator/mariadb-operator-crds
helm install mariadb-operator mariadb-operator/mariadb-operator   --set metrics.enabled=true --set webhook.cert.certManager.enabled=true
```