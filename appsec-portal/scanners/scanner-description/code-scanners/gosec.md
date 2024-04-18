---
description: Gosec is a security scanner for Go programming language code.
---

# Gosec

It is designed to identify potential vulnerabilities in the **Go** codebase, including common issues such as **SQL injections**, **buffer overflows**, and **cross-site scripting (XSS)** vulnerabilities.

[Gosec](https://github.com/securego/gosec) scans Go code by analyzing the _abstract syntax tree (AST)_ of the program. It performs data flow analysis to identify potential security issues and reports them to the user.

One interesting feature of Gosec is its ability to scan for issues in code that has not yet been compiled. This means that developers can catch security issues before they even get a chance to be introduced into the codebase. Gosec is also highly customizable, with options for output formats, severity levels, and more.
