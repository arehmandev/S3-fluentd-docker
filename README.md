# S3-fluentd-docker
Keeping your docker container logs in S3.
Can be run as a daemon on each instance or as a container (dockerfile included, just mount the host volume to the guest volume '/var/lib/docker/containers'

Instructions:
```
1. Clone repo and cd into it.
2. docker build -t s3fluentd .

# If using docker (vanilla)
3. docker run -d -v /var/lib/docker/containers:/var/lib/docker/containers s3fluentd

# If using Kubernetes
3. docker run -d -v /var/log/containers/:/var/lib/docker/containers/ s3fluentd
```

Reference:
https://github.com/fluent/fluent-plugin-s3
https://github.com/kubernetes/kubernetes/tree/master/cluster/addons/fluentd-elasticsearch
