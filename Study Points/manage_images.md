# Manage Images

### Understand private registry security

***`TODO`***

### Interact with many different registries
1. Configuring Registries
- Update `/etc/containers/registries.conf` file
- Edit `registries` entry in the `[registries.search]` section
- Ex: `registries = ["registry.access.redhat.com", "quay.io"]`
- Secure connections require trusted certficate
- To support insecure connection, add registry name to `registries` entry in `[registries.insecure]` section
2. Accessing Registries
- `podman search` to find images by image name/user name/desc. from all registries listed in config. file
- `podman search [OPTIONS] <term>`

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
- ***`TODO`***