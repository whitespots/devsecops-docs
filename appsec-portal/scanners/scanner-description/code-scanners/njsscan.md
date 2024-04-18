# Njsscan

**Auditor Job Name**: Gitlab Nodejs

Gitlab [NodeJsScan ](https://gitlab.com/gitlab-org/security-products/analyzers/nodejs-scan)performs SAST scanning on repositories containing code written in the following language: `javascript`.

The analyzer wraps [njsscan](https://github.com/ajinabraham/njsscan), a tool that checks NodeJS code for CWEs based on [semgrep](https://github.com/returntocorp/semgrep) rules, and is written in Go. It's structured similarly to other Static Analysis analyzers because it uses the shared [command](https://gitlab.com/gitlab-org/security-products/analyzers/command) package.

{% hint style="info" %}
Currently the scanner is only supported in the **Auditor**
{% endhint %}
