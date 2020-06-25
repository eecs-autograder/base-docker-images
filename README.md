# Autograder Sandbox Base Images

This repository contains the source files for supported base images. These images all work with the [Autograder Sandbox](../autograder-sandbox) library and can be inherited from to create new images.

Contributions to this repository are welcome in the form of pull requests. For a base image to be valid, it must contain a user named `autograder`, and a directory of `/home/autograder/working_dir` set as the images `WORKDIR`. The following `Dockerfile` snippet accomplishes this for Ubuntu 16:

```
RUN mkdir -p /home/autograder/working_dir

RUN useradd autograder && \
   mkdir -p /home/autograder/working_dir && \
   chown -R autograder:autograder /home/autograder

WORKDIR /home/autograder/working_dir
```

## Images

This section lists the tags for each supported base image.

`eecsautograder/ubuntu16:latest`: Based on Ubuntu 16 (Xenial)

`eecsautograder/ubuntu18:latest`: Based on Ubuntu 16 (Bionic)
