# Unifi Controller Helm Chart

The UniFi Controller helm chart installs a unifi controller software onto your kubernetes cluster. A Kubernetes cluster (k3s, kind, K8s, or anything else) is required. For exposing the ports, MetalLB or any other LoadBalancer implementation is required.

## Controller ports

The following is a list of ports that are used by the unifi controller. The ports are exposed by a MetalLB service to be discoverable in your network.

|Protocol|Port|Purpose|
|--|--|--|
|UDP|3478|Port used for STUN.|
|UDP|5514|Port used for remote syslog capture|
|TCP|8080|Port used for device and application communication|
|TCP|8443|Port used for application GUI/API as seen in a web browser|
|TCP|8880|Port used for HTTP portal redirection|
|TCP|8843|Port used for HTTPS portal redirection|
|TCP|6789|Port used for UniFi mobile speed test|
|TCP|27117|Port used for local-bound database communication|
|UDP|5656-5699|Ports used by AP-EDU broadcasting|
|UDP|10001|Port used for device discovery|
|UDP|1900|Port used for "Make application discoverable on L2 network" in the UniFi Network settings|

## Further reading

- The original chart from Lukas Bahr: [https://github.com/lukibahr/unifi-controller-helm-chart](https://github.com/lukibahr/unifi-controller-helm-chart)
- Releaser action used for releasing the charts: [https://github.com/helm/chart-releaser-action](https://github.com/helm/chart-releaser-action)
- The image used from linuxserver.io: [https://hub.docker.com/r/linuxserver/unifi-controller](https://hub.docker.com/r/linuxserver/unifi-controller)
- Unifi controller ports: [https://help.ui.com/hc/en-us/articles/218506997-UniFi-Ports-Used](https://help.ui.com/hc/en-us/articles/218506997-UniFi-Ports-Used)
