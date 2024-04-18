# GitLab actions

## Adding new scanners

1. Put scanner version in `common/variables.yml` (**pipelines** repo).
2. Add the `Dockerfile` to the folder in the **security-images** repo.
3. Add the job to the `gitlab-ci.yml` file (i**security-images** repo).
4. Add the job with the scan script in the common folder (**pipelines** repo).
5. Configure the default variables in `common/variables.yml` (**pipelines** repo).
6. Test the new scanner.

## Integration

You can integrate the Security Pipeline with your CI/CD pipeline in two ways: triggering pipelines **without passing any parameters** and triggering pipelines **with specific parameters**.

### Triggering Pipelines Without Passing Any Parameters

This example of `.gitlab-ci.yml` settings will detect all languages/technologies automatically and run checks without parameters.

```yaml
stages: 
  # after build stage
  - security

security:
  stage: security
  allow_failure: true
  trigger:
    include:
    # Path to the shared repo
      - project: 'whitespots-public/pipelines'
        # a proper branch name
        ref: 'main'
        file: 'pipelines.yml'
```

### Triggering Pipelines With Specific Parameters

This is a detailed integration example of `.gitlab-ci.yml`.

```yaml
stages: 
  # after build stage
  - security

security:
  stage: security
  allow_failure: true
  trigger:
    include:
    # Path to the shared repo
      - project: 'whitespots-public/pipelines'
        # a proper branch name
        ref: 'main'
        file: 'pipelines.yml'
  variables:

    # Secrets settings
    SEC_SECRETS_SCAN_ENABLE: "true"

    # SAST settings
    SEC_SAST_ENABLE: "true"
    SEC_GREP: "true"
    SEC_SEMGREP_CONFIG: "p/ci"
    SEC_PYTHON: "true"
    SEC_RUBY: "false"
    SEC_PHP: "false"
    SEC_JS: "true"
    SEC_GOLANG: "false"
    
    # Dependency check settings
    SEC_IMAGE_SCAN_ENABLE: "true"
    SEC_IMAGE_TO_SCAN_NAME: ${CI_REGISTRY_IMAGE}
    SEC_IMAGE_TO_SCAN_TAG: ${CI_COMMIT_REF_NAME}
    SEC_IMAGE_REGISTRY_URL: ${CI_REGISTRY}
    SEC_IMAGE_REGISTRY_USER: ${CI_REGISTRY_USER}
    SEC_IMAGE_REGISTRY_PASS: ${CI_REGISTRY_PASSWORD}

    # DAST settings
    SEC_DAST_ENABLE: "true"
    SEC_DAST_URL_TO_SCAN: "https://example.com"

    # Mobile settings
    SEC_MOBILE_ENABLE: "false"
    SEC_MOBILE_APK_PATH: "./apk/diva-beta.apk"
    SEC_MOBILE_SCAN_TYPE: "apk|ios"
    SEC_CHECKKARLMARX_DOMAIN: 'mycompany.com'
    SEC_CHECKKARLMARX_QA_TAGS: 'qa test dev stage'
    SEC_CHECKKARLMARX_PACKAGES: 'com.mycompany com.example'

    # Infrastructure scanners
    SEC_INFRA_ENABLE: "false"
    SEC_INFRA_DOMAIN: "exxxxample.com"

    # SAST (csharp) settings
    SEC_SONARQUBE_ENABLE: "false"
    SEC_SONARQUBE_URL: "https://sonarqube-test.whitespots.io"
    SEC_SONARQUBE_PROJECT_KEY: "test-app"
    SEC_SONARQUBE_SOURCES: "/usr/src"
    SEC_SONARQUBE_TOKEN: "token"
    SEC_SONARQUBE_PATH_TO_SLN: "token" # <- put in CI/CD variables for security reasons
    
```

### Integration Examples

There are several integration examples provided in the [repository](https://gitlab.com/whitespots-public/pipelines/-/tree/main/integration\_templates), each containing a `.gitlab-ci.yml` file where you can see how to integrate the security checks into your pipelines. Here are a few examples:

* [Python app](https://gitlab.com/whitespots-public/vulnerable-apps/vulnerable-python-app): This example shows the difference between the `include` and `parent-child` approaches.
* [Java app with Gradle and Kotlin](https://gitlab.com/whitespots-public/vulnerable-apps/vulnerable-java-gradle-kotlin)
* [Java app with Gradle](https://gitlab.com/whitespots-public/vulnerable-apps/vulnerable-java-gradle-app)
* [JavaScript app](https://gitlab.com/whitespots-public/vulnerable-apps/vulnerable-js-app)
* [Kubernetes app](https://gitlab.com/whitespots-public/vulnerable-apps/vulnerable-k8s-app)

## Detailed video tutorial from our team

{% embed url="https://www.youtube.com/watch?v=DLN1kNh_Ha0" %}
