## Production level image for kubectl

**Distroless:**
Distroless is a set of Docker images maintained by Google. These images are designed to contain only the necessary dependencies to run a specific application,
it is without any unnecessary packages or utilities found in traditional Linux distributions like Debian or Alpine.

Examples: there are distroless images for python, node.js, java, etc.

// Distroless = "distribution" + "less."

**Image Scanners:** are tools used to inspect container images for security vulnerabilities, compliance issues, or other potential risks before deploying them in a Kubernetes environment. These scanners help ensure that the container images being used are safe and meet the necessary security standards.

Trivy is also an Image Scanner.

Using images like apline linux as base image is better because they don't hae the extra stuff that is ont need, this also means that it will have less security vurnarailities (lesser the stuff, lesser chances of getting hacked).

- **BusyBox** is present in Alpine Linux that consolidates many common UNIX utilities into a single small executable.

To learn more - https://overcast.blog/leveraging-alpine-images-in-kubernetes-a-guide-6245e1380513

From my research and by using Trivy, this is the data I got about potential solutions:

1. cgr.dev/chainguard/kubectl:latest
   
```
cgr.dev/chainguard/kubectl:latest (wolfi 20230201)

Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

2. alpine:latest

```
alpine:latest (alpine 3.19.1)

Total: 2 (UNKNOWN: 0, LOW: 2, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

3. bitnami/kubectl:1.28.6 (not done by me)

```
bitnami/kubectl:1.28.6 (debian 11.9)
====================================
Total: 147 (UNKNOWN: 0, LOW: 95, MEDIUM: 27, HIGH: 22, CRITICAL: 3)
```

### Links

[Alpine](https://hub.docker.com/_/alpine/tags)
[bitnami/kubectl](https://hub.docker.com/r/bitnami/kubectl/tags)
[chainguard/kubectl](https://images.chainguard.dev/directory/image/kubectl/versions#/)
