---
description: AppSec Portal deployment step-by-step guide
---

# Installation

### System Requirements for Portal usage:

* Minimum system resources: 4 GB of RAM and 2 CPU cores.
* Free disk space for installation and data storage of the portal.
* Network access for external users (users must be able to connect to the portal over the network).

### Prerequisites

Before installing the AppSec Portal, make sure you have the following software installed on your machine (for Docker-compose installation type):

* [**Docker**](https://docs.docker.com/get-docker/) (version 19.03 or higher)
* [**Docker Compose**](https://docs.docker.com/compose/install/) (version 1.26 or higher)
* [**SSH keys**](installation.md#ssh-keys) (for GitLab CI installation option)

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

{% hint style="info" %}
Please note that the AppSec Portal is currently incompatible with Amazon Aurora database.
{% endhint %}

### Installation

* Option 1: [**GitLab CI installation**](installation.md#gitlab-ci-installation) (automated docker-compose installation)
* Option 2: [**Install using Helm**](installation.md#install-using-helm) (install in Kubernetes environment)
* Option 3: [**Docker-compose installation**](installation.md#docker-compose-installation) (manual docker-compose installation)

<details>

<summary>GitLab CI installation</summary>

**Step 1:**  Fork the [AppSec Portal repository](https://gitlab.com/whitespots-public/appsec-portal.git). \
This will create a copy of the repository under your account, which you can then modify and configure as needed

**Step 2:** Set the public SSH key [on the host](installation.md#set-ssh-key-to-your-server) where the portal will be deployed. \
Add an SSH key to your [GitLab account](https://docs.gitlab.com/ee/user/ssh.html#add-an-ssh-key-to-your-gitlab-account) \
This key will be used to establish a secure connection between the host and the repository

**Step 3:** [Configure Environment Variables](https://docs.gitlab.com/ee/ci/variables/) for a forked project in GitLab CI/CD settings

* **mandatory** environment variables that **must** be specified \
  (In the CI/CD settings, you need to set the following environment variables for these keys):

<mark style="color:blue;">SEC\_PORTAL\_HOST:</mark> Specify the host where the portal will be deployed                            <mark style="color:blue;">SSH\_KEY\_PRIVATE:</mark> Set the private SSH key within the forked repository. \
This key will be used for authentication during the installation process

* **optional** environment variables. \
  You can choose to **accept** the **default** values provided for demonstration purposes **or specified** it if necessary:

```bash
IMAGE_VERSION=latest
DB_NAME=db_name
DB_USER=db_user
DB_PASS=db_pass
DB_HOST=db_host
DB_PORT=5432
GUNICORN_WORKERS=4
GUNICORN_THREADS=4
IMPORTER_GUNICORN_WORKERS=1
IMPORTER_GUNICORN_THREADS=1
RABBITMQ_DEFAULT_USER=admin
RABBITMQ_DEFAULT_PASS=mypass
AMQP_HOST_STRING=amqp://admin:mypass@rabbitmq:5672/
DOMAIN=http://localhost
COOKIES_SECURE=False (True if you use https)

```

The <mark style="color:blue;">IMAGE\_VERSION</mark> The script will autonomously determine the most recent version

For optimal performance (tested on 1 million findings), it is recommended to specify the following environment values: <mark style="color:blue;">GUNICORN\_WORKERS</mark> = **4** and <mark style="color:blue;">GUNICORN\_THREADS</mark>= **4**\
\
To configure the import worker and import threads, the following is necessary: \
<mark style="color:blue;">IMPORTER\_GUNICORN\_WORKERS</mark> determines the number of workers for processing import tasks. It is recommended to set a value that takes into account the volume and intensity of import tasks. \
<mark style="color:blue;">IMPORTER\_GUNICORN\_THREADS</mark> defines the number of threads within each import worker. This affects the parallel processing of tasks within the worker.&#x20;

<mark style="color:blue;">DB\_NAME</mark>, <mark style="color:blue;">DB\_USER</mark>, <mark style="color:blue;">DB\_PASS</mark>, <mark style="color:blue;">DB\_HOST</mark>, <mark style="color:blue;">DB\_PORT</mark> variables are required for database configuration

If the message broker is hosted on a third-party server, only the <mark style="color:blue;">AMQP\_HOST\_STRING</mark> must be specified. However, if the container is raised locally, all three variables, including <mark style="color:blue;">RABBITMQ\_DEFAULT\_USER</mark> and <mark style="color:blue;">RABBITMQ\_DEFAULT\_PASS</mark> need to be specified. \
The username and password in the RABBITMQ\_DEFAULT\_PASS and RABBITMQ\_DEFAULT\_USER variables **must be the same** as in AMQP\_HOST\_STRING.

The <mark style="color:blue;">COOKIES\_SECURE</mark> variable determines the cookie security flag. It should be set to <mark style="color:purple;">`True`</mark> if HTTPS is used.

**Step 4:** Run pipeline

**Step 5:** Click on **install** section

<img src="../../.gitbook/assets/pipeline (1).png" alt="" data-size="original">

The GitLab CI script provided in the forked repository will handle the installation process

This script will raise the portal and generate a user with administrator privileges **using the default login and password credentials** _**"admin/admin"**_

Please note that after the initial installation, it is **necessary to reset the password** for the administrator user via the Django admin panel:  follow the `<your-domain>.com/admin` URL and sign in using the superuser credentials, then select "**Users**" in the left panel. You can add users from there

**Next step:** [Start your AppSec Portal and apply the licence](get-started-with-the-appsec-portal/)

</details>

<details>

<summary>Install using Helm</summary>

Before using Helm, make sure that Helm is installed on your computer and that your Kubernetes cluster is configured to work with Helm

**Step 1:** Clone the repository

Clone the Appsec portal repository to your server:

```
git clone https://gitlab.com/whitespots-public/appsec-portal.git appsec-portal
```

**Step 2:** Navigate to the root directory

Navigate to the directory where the Appsec-portal files were cloned, the helm directory:

```
cd appsec-portal/AppsecPortal-HelmChart  
```

**Step 3**: Set environment variables

in the **values.yaml** file, change the default environment variables in some sections to meet your requirements :

* <mark style="background-color:blue;">In the</mark> <mark style="background-color:blue;"></mark><mark style="background-color:blue;">**deploymentSpec**</mark> <mark style="background-color:blue;"></mark><mark style="background-color:blue;">section:</mark>

```bash
release: release_v24.08.1
```

* <mark style="background-color:blue;">In the</mark> <mark style="background-color:blue;"></mark><mark style="background-color:blue;">**ingresses**</mark> <mark style="background-color:blue;"></mark><mark style="background-color:blue;">section:</mark>

```bash
- name: ingress-webhook
  path: /api/v1/jira-helper/jira-event/<your-webhook>/
```

Replace _your-webhook_ in path variable '/api/v1/jira-helper/jira-event/your-webhook/' with the unique identifier (token) associated with the specific webhook event, for example, e2b7e8be-1c77-4969-9105-58e91bd311cc.

* <mark style="background-color:blue;">In the</mark> <mark style="background-color:blue;"></mark><mark style="background-color:blue;">**configMap**</mark> <mark style="background-color:blue;"></mark><mark style="background-color:blue;">section:</mark>

```bash
COOKIES_SECURE: "True"  
DB_HOST: "postgres"     
DB_PORT: "5432"         
DB_NAME: "postgres"       
DB_USER: "postgres"      
DEBUG: "True"           
DOMAIN: http://localhost  
RABBITMQ_DEFAULT_USER: admin 
```

* <mark style="color:blue;">`COOKIES_SECURE`</mark>: variable determines the cookie security flag. It should be set to `True` if HTTPS is used.
* <mark style="color:blue;">`DB_NAME`</mark>, <mark style="color:blue;">`DB_USER`</mark>, <mark style="color:blue;">`DB_HOST`</mark>, <mark style="color:blue;">`DB_PORT`</mark> and <mark style="color:blue;">`DB_PASS`</mark> specify the variables needed to configure the database, or use the defaults.
* The <mark style="color:blue;">`DOMAIN`</mark> specify the domain where the Appsec-portal will be accessible.
* if the container is raised locally <mark style="color:blue;">`RABBITMQ_DEFAULT_USER`</mark> need to be specified

<!---->

* <mark style="background-color:blue;">In the</mark> <mark style="background-color:blue;"></mark><mark style="background-color:blue;">**secrets**</mark> <mark style="background-color:blue;"></mark><mark style="background-color:blue;">section:</mark>

```bash
AMQP_HOST_STRING: "amqp://admin:mypass@rabbitmq:5672/"
DB_PASS: "postgres"
JWT_PRIVATE_KEY: <your key>
JWT_PUBLIC_KEY: <your key>
SECRET_KEY: <your key>
RABBITMQ_DEFAULT_PASS: "mypass"
```

* If the message broker is hosted on a third-party server, only the <mark style="color:blue;">`AMQP_HOST_STRING`</mark> must be specified. However, if the container is raised locally, all three variables, including <mark style="color:blue;">`RABBITMQ_DEFAULT_USER`</mark> and <mark style="color:blue;">`RABBITMQ_DEFAULT_PASS`</mark> need to be specified
* The <mark style="color:blue;">`JWT_PRIVATE_KEY`</mark> and <mark style="color:blue;">`JWT_PUBLIC_KEY`</mark> variables are RSA key pair used to sign JWT keys
* <mark style="color:blue;">`SECRET_KEY`</mark>: variable is used to generate hashes in Django

<!---->

* <mark style="background-color:blue;">In the</mark> <mark style="background-color:blue;"></mark><mark style="background-color:blue;">**db**</mark> <mark style="background-color:blue;"></mark><mark style="background-color:blue;">section:</mark>

It is **recommended** to use an **external database**. For this purpose it is enough only to specify the value `true` for the variable <mark style="color:blue;">`external_db`</mark>, other variables in this section do not need to be specified

But if you use a database inside the cluster, configure variables for it

```bash
external_db: false 
name: postgres
storageClassName: local-storage
node: minikube
path: /mnt/local-storage
mountPath: /mnt
claimName: postgres-pv-claim
```

<mark style="color:blue;">`external_db`</mark>: `false`\
<mark style="color:blue;">`name`</mark>: database name\
<mark style="color:blue;">`storageClassName`</mark>: storage class name for the database\
<mark style="color:blue;">`node`</mark>: the node in the cluster that will host the database\
<mark style="color:blue;">`path`</mark>:path to the database storage on the node\
<mark style="color:blue;">`mountPath`</mark>: the place inside the container where the database storage will be mounted\
<mark style="color:blue;">`claimName`</mark>: the name of the PersistentVolumeClaim that is used to request storage allocation

**Step 4:** To configure the ingress

To configure the ingress in your Helm chart, add the required annotations. We recommend including the following:

For **ingress-webhook**:

```bash
ingress.kubernetes.io/scheme: internet-facing
ingress.kubernetes.io/target-type: ip
```

For **ingress-hosts**:

```bash
ingress.kubernetes.io/scheme: internal
ingress.kubernetes.io/target-type: ip
```

For **ingress-import**:

```bash
ingress.kubernetes.io/scheme: internal
ingress.kubernetes.io/target-type: ip
```

**Step 5:** Install the application using Helm

Run the application by executing the following command:

```
helm install appsecportal <path-to-helm-directory>
```

replace _\<path-to-helm-directory>_ with the path to the directory that contains the Helm Chart for your application.

After the first run you will receive an **Access Token**.

<mark style="color:red;">Copy the value of the access token and add it in the</mark> <mark style="color:red;"></mark><mark style="color:red;">**values.yaml**</mark> <mark style="color:red;"></mark><mark style="color:red;">file in the</mark> <mark style="color:red;"></mark><mark style="color:red;">**secret section**</mark> <mark style="color:red;"></mark><mark style="color:red;">and</mark> <mark style="color:red;"></mark><mark style="color:red;">**restart scanner-worker**</mark> <mark style="color:red;"></mark><mark style="color:red;">pod</mark>

**Next step:** [Start your AppSec Portal and apply the licence](get-started-with-the-appsec-portal/)

</details>

<details>

<summary>Docker-compose installation</summary>

**Step 1:** Clone the repository

Clone the AppSec Portal repository to your server:

```bash
git clone https://gitlab.com/whitespots-public/appsec-portal.git appsec-portal
```

**Step 2:** Navigate to the root directory

Navigate to the root directory of the AppSec Portal project by executing the following command:

```bash
cd appsec-portal
```

**Step 3:** Set environment variables

In the root directory of the AppSec Portal project, execute the following command:

<pre class="language-bash"><code class="lang-bash"><strong>./set_vars.sh
</strong></code></pre>

The script prompts you for values for the following environment variables, including optional ones. You can also accept the default values for optional variables by pressing Enter:

<pre class="language-bash"><code class="lang-bash">DB_NAME{default=postgres}
DB_USER{default=postgres}
DB_PASS{default=postgres}
DB_HOST{default=postgres}
DB_PORT{default=5432}
<strong>RABBITMQ_DEFAULT_USER{default=admin}
</strong><strong>RABBITMQ_DEFAULT_PASS{default=mypass}
</strong><strong>AMQP_HOST_STRING{default=amqp://admin:mypass@rabbitmq:5672/}
</strong>COOKIES_SECURE{default=True}
<strong>DOMAIN=http://localhost
</strong>IMAGE_VERSION=release_v24.08.1 

</code></pre>

* The <mark style="color:blue;">`IMAGE_VERSION`</mark> the <mark style="color:red;">required</mark> variable must be specified. Specify a [specific version](../release-notes.md), e.g. release\_v24.08.1
* The <mark style="color:blue;">`DOMAIN`</mark>the <mark style="color:red;">required</mark> variable must be specified. Specify the domain where the AppSec Portal will be accessible
* <mark style="color:blue;">`DB_NAME`</mark>, <mark style="color:blue;">`DB_USER`</mark>, <mark style="color:blue;">`DB_PASS`</mark>, <mark style="color:blue;">`DB_HOST`</mark>, <mark style="color:blue;">`DB_PORT`</mark> <mark style="color:green;">optional variable</mark><mark style="color:blue;">.</mark> Specify the variables needed to configure the database, or use the defaults.
* If the message broker is hosted on a third-party server, only the <mark style="color:blue;">`AMQP_HOST_STRING`</mark> must be specified. However, if the container is raised locally, all three variables, including <mark style="color:blue;">`RABBITMQ_DEFAULT_USER`</mark> and <mark style="color:blue;">`RABBITMQ_DEFAULT_PASS`</mark> need to be specified\
  The username and password in the RABBITMQ\_DEFAULT\_PASS and RABBITMQ\_DEFAULT\_USER variables **must be the same** as in AMQP\_HOST\_STRING.
* The <mark style="color:blue;">`COOKIES_SECURE`</mark> variable determines the cookie security flag. It should be set to <mark style="color:purple;">`True`</mark> if HTTPS is used

The set\_vars.sh script creates the .env file with the configured environment variables and generates a pair of JWT keys, which are used to sign JWT keys and SECRET\_KEY is used to generate hashes in Django.

<mark style="background-color:red;">DO NOT run the ./set\_vars.sh command twice.</mark> \
If you need to change the value of a variable, do so in the .env file.

**Step 4:** Start the AppSec Portal

To start the AppSec Portal, run the following command:

```bash
sh run.sh
```

**Step 5:** Create a superuser account

To create an administrator account, execute the following command:

```bash
docker-compose exec back python3 manage.py createsuperuser --username admin
```

<img src="../../.gitbook/assets/setup.png" alt="" data-size="original">

This username and password will allow you to **log in to** the installed **Appsec Portal**

or

Create users using Django admin panel

In order to access admin settings, follow the `<your-domain>.com/admin` URL and sign in using the superuser credentials, then select **Users** in the left panel. You can add users from there. Don't forget to assign the necessary permissions to the users.

<img src="../../.gitbook/assets/django1.png" alt="" data-size="original">

<img src="../../.gitbook/assets/django 2.png" alt="" data-size="original">

**Next step:** [Start your AppSec Portal and apply the licence](get-started-with-the-appsec-portal/)

</details>

Congratulations, you have successfully installed the AppSec Portal! \
<mark style="background-color:green;">Now</mark> [<mark style="background-color:green;">**apply the licence**</mark>](get-started-with-the-appsec-portal/) <mark style="background-color:green;">to your installed application.</mark>

> If you have any issues during the installation process or while using the app, contact our support team _**sales@whitespots.io**_ for assistance:heart:.
