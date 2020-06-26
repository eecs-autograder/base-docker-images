# Autograder Sandbox Base Images

This repository contains the source files for supported base images. These images all work with the [Autograder Sandbox](../autograder-sandbox) library and can be inherited from to create new images.

Contributions to this repository are welcome in the form of pull requests. Each base image should be placed in a separate directory in the top-level directory of this repo. Those image-specific directories should contain a file named `Dockerfile` and any other files needed to build the image. For a base image to be valid, it must meet the following requirements:
- A user named `autograder` must exist
- A directory of `/home/autograder/working_dir` must be set as the image's `WORKDIR` and must be owned by the autograder user. 
- Python 3.5 or greater must be installed and available on the system PATH.

The following `Dockerfile` snippet accomplishes this for Ubuntu 16:

```
RUN apt-get update --fix-missing && apt-get install -y python3

RUN mkdir -p /home/autograder/working_dir

RUN useradd autograder && \
   mkdir -p /home/autograder/working_dir && \
   chown -R autograder:autograder /home/autograder

WORKDIR /home/autograder/working_dir
```

## Images

This section lists the tags for each supported base image.

`eecsautograder/ubuntu16:latest`: Based on Ubuntu 16 (Xenial)

`eecsautograder/ubuntu18:latest`: Based on Ubuntu 18 (Bionic)
