---
description: Auditor step-by-step deployment guide
---

# Installation

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

## System Requirements for Auditor usage:

* Minimum system resources: 4 GB of RAM and 2 CPU cores.
* Free disk space for installation and data storage of the Auditor.
* Network access to and from the portal and to the location of your asset (the location of the product to be scanned).

## Prerequisites

Before installing the Auditor, make sure you have the following software installed on your machine:

**Type of installation using containers:**

* [**Docker**](https://docs.docker.com/get-docker/) (version 19.03 or higher)
* [**Docker Compose**](https://docs.docker.com/compose/install/linux/#install-using-the-repository) (version 1.26 or higher)
* [**SSH keys**](installation.md#ssh-keys) (for GitLab CI installation option)

**Installation in Kubernetes environment:**

* **Helm configured with Kubernetes cluster**

<details>

<summary>SSH keys generation</summary>

To securely connect to the Linux server, you will need to set up SSH keys.

If you don't have SSH keys already, you can generate them using the following command in your server terminal:

```bash
ssh-keygen 
```

:warning: When copying keys, make sure you copy **without spaces**.

#### Set SSH key to your Server

After generating the SSH keys, you need to copy the **public SSH key** to the Linux server. Use this command to copy the public key:

```bash
ssh-copy-id <username>@<server-ip-address>
```

Replace `<username>` with your Linux server account username, and `<server-ip-address>` with the IP address of the Linux server. You will be prompted to enter your password for authentication.

Open the file on your local machine where the **private SSH key** is stored. The private key is typically saved with a `.pem` or `.ssh` file extension.

Select and copy the contents of the private key file. Ensure you copy the key with the correct permissions and line breaks intact.

</details>

## Installation

* Option 1:[ **GitLab CI installation** ](installation.md#gitlab-ci-installation-ansible-playbook)Ansible playbook (automated docker-compose installation)
* Option 2: [**Install using Helm**](installation.md#instal-using-helm) (install in Kubernetes environment)
* Option 3:[ **Docker-compose installation**](installation.md#docker-compose-installation) (manual docker-compose installation)

<details>

<summary>GitLab CI installation (Ansible playbook)</summary>

**Step 1. Fork the Auditor Repository**

Fork the Auditor repository on GitLab. This creates a copy of the repository under your GitLab account.

**Step 2. Set the public SSH key on the host**

Establish a secure connection between the host and the repository by setting the public SSH key.

**Step 3.** [**Configure GitLab CI/CD Environment Variables**](https://docs.gitlab.com/ee/ci/variables/)

In GitLab, go to _"Settings" > "CI / CD" > "Variables"_ and configure the following environment variables:

* <mark style="color:blue;">`SSH_KEY_PRIVATE`</mark>: Set the private SSH key within the forked repository for authentication.
* <mark style="color:blue;">`ACCESS_TOKEN`</mark>: set the Access Token value that you will receive after the first run of CI Pipeline (step 9)

**Optional** environment variables:

* <mark style="color:blue;">`IMAGE_VERSION`</mark>: The script will autonomously determine the most recent version.
* <mark style="color:blue;">`DB_NAME`</mark>, <mark style="color:blue;">`DB_USER`</mark>, <mark style="color:blue;">`DB_PASS`</mark>, <mark style="color:blue;">`DB_HOST`</mark>, <mark style="color:blue;">`DB_PORT`</mark>: Required for database configuration.
*   <mark style="color:blue;">`RABBITMQ_DEFAULT_USER`</mark>, <mark style="color:blue;">`RABBITMQ_DEFAULT_PASS`</mark>, <mark style="color:blue;">`AMQP_HOST_STRING`</mark>: Message broker configuration.&#x20;

    The username and password in the RABBITMQ\_DEFAULT\_PASS and RABBITMQ\_DEFAULT\_USER variables **must be the same** as in AMQP\_HOST\_STRING.

**Step 4. Update the Hosts File**

In the repository's **`hosts`** file, specify the group name and IP address of the hosts where Auditor will be installed:

`[prod_portal]` - name of the group\
`206.189.63.52` - IP address

**Step 5. Update Variables in prod\_portal.yml**

Update the variables in the **`prod_portal.yml`** file in the\
**group\_vars** directory

```
ansible_user: root 
ansible_ssh_private_key : ~/.ssh/id_rsa
work_dir: /opt
```

<mark style="color:blue;">`ansible_user`</mark>: Specify the user Ansible should use when connecting to the server\
<mark style="color:blue;">`ansible_ssh_private_key`</mark>: Specify the path to the private SSH key for authentication\
<mark style="color:blue;">`work_dir`</mark>: The working directory on the target server where the application will be installed

**Step 6. Commit Changes**

After updating the hosts file and group\_vars/prod\_portal.yml, commit the changes to your GitLab repository

**Step 7. Run GitLab CI Pipeline**

In the GitLab CI/CD > Pipelines section, you should see the pipeline running the deploy job.

**Step 8. Monitor the Installation**

Once the pipeline is running, click on the deploy job to view the logs.\
The Ansible playbook will be executed, deploying Auditor on the specified host.\


<img src="../../.gitbook/assets/ci_deploy.jpg" alt="" data-size="original">

**Step 9. Adding an Access Token**

Now your application should be accessible on the port specified in the configuration.

After the first run, you will receive an <mark style="color:blue;">**`Access Token`**</mark>.

<img src="../../.gitbook/assets/acsess token.jpg" alt="" data-size="original">

<mark style="color:red;">Copy the value of the access token and add it in the CI/CD variables on GitLab</mark>

<mark style="color:blue;">`ACCESS_TOKEN`</mark>: your value

After adding the variable, **must to restart the service** from the command line using the command:

```
docker-compose down
docker-compose up -d
```

Save the key value in a safe place for later usage in the Auditor [settings](../../appsec-portal/auditor/auditor-settings/auditor-configurator.md)

</details>

<details>

<summary>Install using Helm</summary>

Before using Helm, make sure that Helm is installed on your computer and that your Kubernetes cluster is configured to work with Helm

**Step 1. Add helm package**

Add the Auditor package to your server:

```
helm repo add auditor https://gitlab.com/api/v4/projects/51993931/packages/helm/stable
```

**Step 2. Set environment variables**

change the default environment variables to meet your requirements:

* In the **deploymentSpec** section:

```
    global.image.tag=release_v24.07.2 
```

* In the **configMap** section:

```
  configs.configMap.database.host=your_db_host
  configs.configMap.redis.host=your_redis_host
  postgresql.auth.database=appsec
  postgresql.auth.username=appsec
  postgresql.containerPorts.postgresql=5432
  configs.configMap.database.host=your_db_host
  rabbitmq.auth.username=admin           
  rabbitmq.containerPorts.amqp=5672 
```

* In the **secrets** section:

```
  postgresql.auth.password=appsec
  rabbitmq.auth.password=admin
  redis.auth.password="11110000"
```

<mark style="color:blue;">`global.image.tag`</mark>`:` specify a particular release identifier\
<mark style="color:blue;">`postgresql.auth.database`</mark>, <mark style="color:blue;">`postgresql.auth.username`</mark>, <mark style="color:blue;">`configs.configMap.database.host`</mark>, <mark style="color:blue;">`postgresql.containerPorts.postgresql`</mark> and <mark style="color:blue;">`postgresql.auth.password`</mark> variables are required for database configuration.\
For message broker <mark style="color:blue;">`rabbitmq.auth.username`</mark>, <mark style="color:blue;">`rabbitmq.auth.password`</mark> and <mark style="color:blue;">`rabbitmq.containerPorts.amqp`</mark> need to be specified\
<mark style="color:blue;">`redis.auth.password`</mark> If the broker is hosted on a third-party server leave the variable at its default value

**Step 3. Helm install with all resources inside cluster**

In the example we use pre-installed nginx ingress controller and postgres, redis, rabbitmq from chart:

```
helm install auditor auditor/appsecauditor --set postgresql.enabled=true
  --set ingress.enabled=true --set ingress.annotations."nginx\.ingress\.kubernetes\.io\/scheme"=internet-facing
  --set ingress.annotations."nginx\.ingress\.kubernetes\.io\/target\-type"=ip
  --set ingress.ingressClassName=nginx --set ingress.host=your_own_host -n <namespace>

```

After the first login you will receive an <mark style="color:blue;">**`Access Token`**</mark>.&#x20;

<img src="../../.gitbook/assets/acsess token.jpg" alt="" data-size="original">

<mark style="color:red;">Copy and set</mark> <mark style="color:red;">as a variable token</mark> and relaunch service scanner\_worker.

```
kubectl get deployments -n <namespace>
kubectl delete deployment <scanner_runner> -n <namespace>
helm upgrade auditor auditor/appsecauditor --set postgresql.enabled=true
    --set ingress.enabled=true --set ingress.annotations."nginx\.ingress\.kubernetes\.io\/scheme"=internet-facing
    --set ingress.annotations."nginx\.ingress\.kubernetes\.io\/target\-type"=ip
    --set ingress.ingressClassName=nginx --set configs.secret.access_token=your_token --set ingress.host=your__own_host -n <namespace>

```

Save the key value in a safe place for later usage in the Auditor [settings](../../appsec-portal/auditor/auditor-settings/auditor-configurator.md)

</details>

<details>

<summary>Docker-compose installation</summary>

**Step 1: Clone the repository**

Clone the Auditor repository to your server:

```
git clone https://gitlab.com/whitespots-public/auditor.git auditor
```

**Step 2 Navigate to the root directory**

Navigate to the root directory of the Auditor project by executing the following command:

```
cd auditor
```

**Step 3: Set environment variables**

Environment variables are set by default.\
If changes are needed, create an **.env** **file** in the project's root folder.&#x20;

Example .env file:

```
IMAGE_VERSION=release_v24.07.2
DB_NAME=postgres
DB_USER=postgres
DB_PASS=postgres
DB_HOST=postgres
DB_PORT=5432
RABBITMQ_DEFAULT_USER=admin
RABBITMQ_DEFAULT_PASS=mypass
AMQP_HOST_STRING=amqp://admin:mypass@rabbitmq:5672/
DOCKER_ENCRYPTION_TOKEN=defaultvaluetobechangedorelse...
ACCESS_TOKEN=<your value>
```

* <mark style="color:blue;">`IMAGE_VERSION`</mark>the <mark style="color:red;">required</mark> variable must be specified. Specify a [specific version](../release-notes.md), e.g. release\_v24.07.2
* <mark style="color:blue;">`DB_NAME`</mark>, <mark style="color:blue;">`DB_USER`</mark>, <mark style="color:blue;">`DB_PASS`</mark>, <mark style="color:blue;">`DB_HOST`</mark>, <mark style="color:blue;">`DB_PORT`</mark> variables are required for database configuration.
* If the message broker is hosted on a third-party server, only the <mark style="color:blue;">`AMQP_HOST_STRING`</mark> must be specified. However, if the container is raised locally, all three variables, including <mark style="color:blue;">`RABBITMQ_DEFAULT_USER`</mark> and <mark style="color:blue;">`RABBITMQ_DEFAULT_PASS`</mark> need to be specified.\
  The username and password in the RABBITMQ\_DEFAULT\_PASS and RABBITMQ\_DEFAULT\_USER variables **must be the same** as in AMQP\_HOST\_STRING.
* <mark style="color:blue;">`DOCKER_ENCRYPTION_TOKEN`</mark> this variable is essential when accessing images from a private registry. If your registry requires authentication, provide the appropriate encryption token here.
* <mark style="color:blue;">ACCESS\_TOKEN</mark>: After the first run of the Auditor (step 4) you will get the value of the access token. You must to copy it and put this variable and its value in the .env file.

**Step 4. Start the Auditor**

From the terminal command line, navigate to the directory where the docker-compose.yml file is located.

Run the application by executing the following command:

```
docker-compose up -d
```

This will start all the services described in the docker-compose.yml file in the background.

After successfully running the docker-compose up -d command, your application should be accessible on the port specified in the configuration.

You will receive an <mark style="color:blue;">**`Access Token`**</mark> the first time you start. \
<mark style="color:red;">Copy it and set it in the .env file</mark> as the value of the variable <mark style="color:blue;">ACCESS\_TOKEN</mark> (step 3)

<img src="../../.gitbook/assets/acsess token.jpg" alt="" data-size="original">

After adding the variable, **must to restart the service** from the command line using the command:

```
docker-compose down
docker-compose up -d
```

Save the key value in a safe place for later usage in the Auditor [settings](../../appsec-portal/auditor/auditor-settings/auditor-configurator.md)

</details>

