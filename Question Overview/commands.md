## EX180 Podman Commands

1. R - run | creates a container
- -d runs in background
- --name sets the name
- -p exposes ports to host machine
- -e sets env variables
2. B - build | builds a dockerfile and produces an image
3. T - tag | tags an image
4. S - save | saves an images
- -o specifies the output file name
5. L - logs | shows logs
- --tail use it to see the last X lines of logs (ex: `--tail=10 <container_name>`)
6. R - rm | removes the container
7. S - stop | stops the container
8. P - push | pushes the images to an images repository
