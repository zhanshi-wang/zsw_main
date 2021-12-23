FROM ubuntu:20.04

RUN apt-get update -qq \
    && apt-get upgrade -qq \
    && apt-get autoclean -y \
    && apt-get autoremove -y
RUN useradd -ms /bin/bash code

RUN apt-get install -y build-essential

WORKDIR /home/code
COPY ./ ./

RUN make -B

USER code
CMD ["/bin/bash"]