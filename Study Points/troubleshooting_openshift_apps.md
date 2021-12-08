# Troubleshoot Applications in OpenShift

### Understand the description of application resources

***`TODO`***

### Get application logs
- `podman exec [options] container command [arguments]`
- Ex: `podman exec apache-container cat /var/log/httpd/error_log`
- `oc exec [options] pod [-c container] -- command [arguments]`
- Ex: `oc exec -it myhttpdpod /bin/bash`

### Inspect running applications

***`TODO`***

### Connecting to containers running in a pod

***`TODO`***

### Copy resources to/from containers running in a pod

***`TODO`***