# ivdata/snapclient docker image modified
FROM debian:buster-slim

ARG SNAPCAST_VERSION=0.26.0
ARG TARGETARCH
ENV SNAPCAST_CLIENT_HOST_ID=snapcast-client
ENV SNAPCAST_SERVER_HOST=snapcast-server
ENV SNAPCAST_SERVER_PORT=1704
ENV SNAPCAST_CLIENT_INSTANCE_ID=1

RUN  apt-get update \
  && apt-get install -y wget ca-certificates \
  && rm -rf /var/lib/apt/lists/*
RUN  wget https://github.com/badaix/snapcast/releases/download/v${SNAPCAST_VERSION}/snapclient_${SNAPCAST_VERSION}-1_without-pulse_$(echo $TARGETARCH | sed 's/arm/armhf/g').deb
RUN  dpkg -i snapclient_${SNAPCAST_VERSION}-1_without-pulse_$(echo $TARGETARCH | sed 's/arm/armhf/g').deb \
  ;  apt-get update \
  && apt-get -f install -y \
  && rm -rf /var/lib/apt/lists/*
RUN /usr/bin/snapclient -v
ENTRYPOINT ["/bin/bash","-c","/usr/bin/snapclient --host $SNAPCAST_SERVER_HOST --hostID $SNAPCAST_CLIENT_HOST_ID --port $SNAPCAST_SERVER_PORT --instance $SNAPCAST_CLIENT_INSTANCE_ID"]
