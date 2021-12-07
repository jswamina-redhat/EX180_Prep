# Manage Images

### Understand private registry security

`Temp`

### Interact with many different registries

`Temp`

### Understand and use image tags
- Supports multiple releases of same image
- Useful for multiple versions of same software (container or latest updates of saem software)

### Push and pull images from and to registries
1. Pull
-  `podman pull`
- `podman pull [OPTIONS] [REGISTRY[:PORT]/]NAME[:TAG]`
- `podman pull quay.io/bitnami/nginx`
- `podman pull registry.redhat.io/rhel8/mysql-80:1`
2. Push
- `podman push`
- `podman push [OPTIONS] IMAGE [DESTINATION]`
- `podman push quay.io/bitnami/nginx`
- Image must reside in Podman local storage and be tagged for id purposes in order to publish to registry

### Back up an image with its layers and meta data vs. backup a container state
1. Backup Layers + Metadata
- `podman save [-o FILE_NAME] IMAGE_NAME[:TAG]` 
- `podman save -o mysql.tar registry.redhat.io/rhel8/mysql-80`
2. Backup Container State
- ***TODO***