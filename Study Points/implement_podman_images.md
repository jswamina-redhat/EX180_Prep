# Implement Images Using Podman

### Understand and use FROM (the concept of a base image) instruction
- Specifies base image
- First non-comment instruction in a Containerfile/Dockerfile
- Ex: `FROM ubi8/ubi8:8.2`

### Understand and use RUN instruction
- Executes commands in a new layer on top of current image
- Uses /bin/sh shell
- Ex: `RUN yum install -y httpd`

### Understand and use ADD instruction
- Copies files/folders from local/remote source
- Adds to container's file system
- If used to copy local files, those must be in working dir
- Unpacks local `.tar` files
- Ex: `ADD http://someserver.com/filename.pdf /var/www/html`

### Understand and use COPY instruction
- Copies files from working dir and adds to container's file system
- Not possible to copy a remote file w/ `COPY`
- Ex: `COPY ./src/ /var/www/html/`

### Understand the difference between ADD and COPY instructions
1. Shell Form:
- `ADD <_source_ >... <_destination_ >`
- `COPY <_source_ >... <_destination_ >`
2. Exec Form:
- `ADD ["<_source_ >",... "<_destination_ >"]`
- `COPY ["<_source_ >",... "<_destination_ >"]`
- If *source* is file system path, must be within working dir
- `ADD` allows to specify resource using a URL
- `ADD` will decompress a compressed *source* file to its *destination*, `COPY` cannot

### Understand and use WORKDIR and USER instructions
- `USER`: specifies username or UID to use when running container image for `RUN`, `CMD`, and `ENTRYPOINT`
- Define a user other than `root` for security reasons
- `WORKDIR`: ***TODO***

### Understand security-related topics

***TODO***

### Understand the differences and applicability of CMD vs ENTRYPOINT instructions
1. Exec form (using a JSON array, Preferred]:
- `ENTRYPOINT ["command", "param1", "param2"]`
- `CMD ["param1", "param2"]`
2. Shell form:
- `ENTRYPOINT command param1 param2`
- `CMD param1 param2`
- Containerfile should have at most one `ENTRYPOINT` and `CMD`
- `ENTRYPOINT ["/bin/date", "+%H:%M"]` vs 
- `ENTRYPOINT ["/bin/date"]`
- `CMD ["+%H:%M"]`

### Understand ENTRYPOINT instruction with param
- Specifies the default command to execute when the image runes in a container
- If ommitted, default `ENTRYPOINT` is `/bin/sh -c`
- `CMD` provides default args for `ENTRYPOINT`

### Understand when and how to expose ports from a Docker file
- `EXPOSE` command
- Indicates that container listens to specified network port at runtime
- Defines metadata only, does **NOT** make ports accessible from the host
- Use `-p` option in `podman run` command to expose container ports from the host

### Understand and use environment variables inside images

`TODO`

### Understand ENV instruction
- Defines environment vars that are available in container
- Can declare multiple `ENV` instructions
- `env` command inside container to view env vars

### Understand container volume

`TODO`

### Mount a host directory as a data volume

`TODO`

### a. Understand security and permissions requirements related to this approach

`TODO`

### b. Understand lifecycle and cleanup requirements of this approach

`TODO`