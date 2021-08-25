# Docker Label

really? going back to stuff that make sense

- used to present metadata (label container/images, organize image, build date,etc)


```bash
# Build Dockerfile
docker build --build-arg buildDate=$(date +'%Y-%m-%d') --tag mybusybox .

# Create container out of build image
docker run --name mybusybox-container mybusybox

# Get label from running container
docker inspect --format='{{.Config.Labels.buildDate}}' mybusybox-container

```

- More in labelling container

```bash
# Type : Primary and Secondary
docker run --name mybusylife-container-1 --label type=primary mybusybox
docker run --name mybusylife-container-2 --label type=secondary mybusybox

# Inspect label
docker inspect --format='{{.Config.Labels.type}}' mybusylife-container-1
docker inspect --format='{{.Config.Labels.type}}' mybusylife-container-2

```


[Following]
+ https://forketyfork.medium.com/docker-labels-and-how-to-use-them-614ee1a4c190
