FROM ghcr.io/graalvm/graalvm-ce:ol9-java17

LABEL       author="Noelle Wang" maintainer="Noelle Wang"

RUN         microdnf update -y \
            && mircodnf install -y lsof curl ca-certificates openssl git tar fontconfig tzdata iproute \
            && useradd -d /home/container -m container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]