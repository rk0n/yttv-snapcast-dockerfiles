# Dockerized Snapcast Server Client YouTubeTV Configuration

.
├── README.md
├── sink.sh
├── snapcast-client
│        └── docker-compose.yml
├── snapcast-server
│        ├── docker-compose.yml
│        └── snapserver.conf
└── yttv -> ../../../github/yttv


```
#!/bin/zsh

pacmd load-module module-pipe-sink file=/tmp/snapcast.0 sink_name=snapcast.0
pacmd load-module module-pipe-sink file=/tmp/snapcast.1 sink_name=snapcast.1
```
