# kibanaRefreshFields
Refresh kibana index fields via kibanas API for Elastic stack versions <7.11. The index pattern field list is no longer cached as of 7.11
## Expected variables
I have this setup in my ~/.bashrc, another deployment would be to place this in k8s.
```/bin/bash
export KIBANA_USERNAME=jmainguy
export KIBANA_PASSWORD="supersecret"
export KIBANA_URL=logs-lab.example.com
export KIBANA_INDEX="filebeat-*"
# Optional, if you want to filter out some fields
export KIBANA_FILTER="kubernetes.labels.jenkins"
# Optional, if you want to connect with a spefic tls certificate
export KIBANA_CERT="/tmp/self_signed.crt"
# Optional, if you want to connect without verifying the TLS security, simliar to curl -k
export KIBANA_INSECURE="true"
```

## Usage
```/bin/bash
./kibanaRefreshFields
```

## PreBuilt Binaries
Grab Binaries from [The Releases Page](https://github.com/Jmainguy/kibanaRefreshFields/releases)

## Build
```/bin/bash
export GO111MODULE=on
go build
```
