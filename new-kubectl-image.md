## Production level image for kubectl

**Distroless:**
Distroless is a set of Docker images maintained by Google. These images are designed to contain only the necessary dependencies to run a specific application,
it is without any unnecessary packages or utilities found in traditional Linux distributions like Debian or Alpine.

Examples: there are distroless images for python, node.js, java, etc.

// Distroless = "distribution" + "less."

**Image Scanners:** are tools used to inspect container images for security vulnerabilities, compliance issues, or other potential risks before deploying them in a Kubernetes environment. These scanners help ensure that the container images being used are safe and meet the necessary security standards.

Trivy is also an Image Scanner.
