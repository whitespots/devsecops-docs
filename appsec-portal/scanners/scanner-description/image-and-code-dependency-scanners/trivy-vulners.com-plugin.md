---
description: >-
  Find vulnerabilities, misconfigurations, secrets, SBOM in containers,
  Kubernetes, code repositories, clouds and more
---

# Trivy vulners.com plugin

**Auditor Job Name**: Vulners Trivy\
**Auditor image:** registry.gitlab.com/whitespots-public/security-images/trivy:0.46.0\
**AppSec Portal Importer Name**: Vulners Trivy

Trivy is a versatile security scanning tool designed to identify potential vulnerabilities in both **container images** and **code repositories** (two operating modes). It offers comprehensive coverage of potential security issues, including known vulnerabilities in operating system packages and application dependencies.

Trivy's container scanning capabilities are particularly noteworthy, as it can inspect Docker images for vulnerabilities within OS packages, libraries, and other components. This ensures that containerized applications are built on a secure foundation, minimizing the risk of exploitation through known vulnerabilities.

In addition to container scanning, Trivy also supports code scanning by examining code repositories for security issues.

## How to use it in our portal

There's a dedicated job in Auditor with all required commands

<figure><img src="../../../../.gitbook/assets/image (137).png" alt=""><figcaption></figcaption></figure>

All you have to do here is to define the **`VULNERS_API_KEY`** variable to get valuable details about vulnerabilities. \
(More details: [https://github.com/vulnersCom/trivy-plugin-vulners-db?tab=readme-ov-file](https://github.com/vulnersCom/trivy-plugin-vulners-db?tab=readme-ov-file))

<figure><img src="../../../../.gitbook/assets/image (138).png" alt=""><figcaption></figcaption></figure>

That's it. Now you are ready to create validation rules based on provided descriptions\


<figure><img src="../../../../.gitbook/assets/vulners trivy.jpeg" alt=""><figcaption></figcaption></figure>

