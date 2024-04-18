---
description: All pipeline scanners you need in one place!
---

# 🔘 Features

Discover our [**Security Pipeline repository**](https://gitlab.com/whitespots-public/pipelines) on GitLab. This repository includes a comprehensive set of scanners to address various security aspects.

You can [add and manage](install/) different groups of scan:

<figure><img src="../.gitbook/assets/image (40).png" alt=""><figcaption></figcaption></figure>

* **Secret scanners** such as _Gitleaks_ and _Trufflehog3_ (a fork from _Trufflehog_ specifically for DefectDojo) are used to detect sensitive data that may have been inadvertently committed to version control or shared in other ways.
* **Code scanners** like _Bandit_ (Python), _Brakeman_ (Ruby on Rails), _Eslint_, _Retirejs_ (JavaScript) _Gosec_ (Go), _Semgrep_, _Sonarqube_, _Spotbugs_ (Java), _Hadolint_ (Dockerfiles), _Terrascan_ (Infrastructure as Code), _Gixy_ (NGINX), _Chekhov (IaC formats)_**,**  _Snyk (_open source_)_ are used to detect code issues, vulnerabilities, and other security-related issues in the application codebase.
* **Code dependency** scanners such as _Trivy_ are used to detect security vulnerabilities in code dependencies used by the application.
* **Image dependency scanners** such as _Trivy_ and _Grype_ are used to detect vulnerabilities in Docker images built from public scanners.
* **Dynamic scanners** like _Arachni_ and _OWASP ZAP_ are used to test the application for vulnerabilities while it is running.
* **Infrastructure scanners** like _Subfinder_ and _Nuclei_ are used to scan the infrastructure components like domains and servers for vulnerabilities and security issues.

All these checks are run in transparent mode and **don't affect your build/deploy time.**
