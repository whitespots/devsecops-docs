---
description: How to update Auditor
---

# Update

* [**Option 1: Using containers**](update.md#user-content-using-the-containers):
  * Update using GitLab CI (Ansible playbook)
  * Manual update
* [**Option 2: For Kubernetes environment**](update.md#user-content-update-in-kubernetes-environment):
  * Update using Helm

To update the Auditor to the latest version, follow these steps:

## Using the containers: <a href="#user-content-using-the-containers" id="user-content-using-the-containers"></a>

### Update using GitLab CI (Ansible playbook) <a href="#user-content-update-using-gitlab-ci-ansible-playbook" id="user-content-update-using-gitlab-ci-ansible-playbook"></a>

For the update it is enough to run pipeline and the script will autonomously update Auditor to the latest version&#x20;

<figure><img src="../../.gitbook/assets/ci_deploy (1).jpg" alt=""><figcaption></figcaption></figure>

### Manual update <a href="#user-content-manual-update" id="user-content-manual-update"></a>

1. Stop the application:

```
docker-compose down -v
```

This will stop all services and remove the associated volumes, which will clean up the environment.&#x20;

2. &#x20;Pull the latest changes from the repository:

```
git pull
```

This ensures that you have the most up-to-date codebase to work with.

3. Restart the application:

```
docker-compose up -d
```

## Update in Kubernetes environment: <a href="#user-content-update-in-kubernetes-environment" id="user-content-update-in-kubernetes-environment"></a>

1. To update, run the following command:

```
helm repo update auditor
helm upgrade auditor auditor/appsecauditor
```

replace with the path to the directory that contains the Helm Chart for your application.
