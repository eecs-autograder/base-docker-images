FROM ubuntu:jammy

RUN apt-get update --fix-missing
RUN apt-get install -y build-essential
RUN apt-get install -y python3 python3-pip

RUN mkdir -p /home/autograder/working_dir

RUN useradd autograder && \
   mkdir -p /home/autograder/working_dir && \
   chown -R autograder:autograder /home/autograder

WORKDIR /home/autograder/working_dir

CMD ["/bin/bash"]

