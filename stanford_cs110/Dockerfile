FROM ubuntu:20.04

RUN apt-get update -qq \
    && apt-get upgrade -qq \
    && apt-get autoclean -y \
    && apt-get autoremove -y
RUN useradd -ms /bin/bash code

RUN DEBIAN_FRONTEND=noninteractive \
    TZ=America/Los_Angeles \
    apt-get install -y \
    build-essential \
    libssl-dev \
    bison \
    flex \
    libreadline-dev \
    libxml2-dev \
    socket++

WORKDIR /home/code
COPY ./assign1/slink/actordata /usr/class/cs110/samples/assign1/
COPY ./assign1/slink/moviedata /usr/class/cs110/samples/assign1/
COPY ./ ./

RUN make -B -C ./extra/src/random
RUN make -B -C ./extra/src/threads

# RUN make -B -C ./assign1
# RUN make -B -C ./assign2
# RUN make -B -C ./assign3
# RUN make -B -C ./assign4
# RUN make -B -C ./assign5
RUN make -B -C ./assign6
RUN make -B -C ./assign7
RUN make -B -C ./assign8

USER code
CMD ["/bin/bash"]
