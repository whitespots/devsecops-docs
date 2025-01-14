# Job configuration

Each job (scanner) has a preset configuration that can be changed or supplemented as necessary.



* **Job Type**:  determines the [technical](technical-jobs.md) or [scanner](scanner-jobs.md) job

<figure><img src="../../../../.gitbook/assets/job conf1.png" alt=""><figcaption></figcaption></figure>



* **Shared Volume**: in activated position passes its scan results to the next jobs in the sequence

<figure><img src="../../../../.gitbook/assets/job conf 2.png" alt=""><figcaption></figcaption></figure>

* **Image**: contains the address of the job's image registry. \
  If you are using your own job, change the address of the registry and specify its credentials

<figure><img src="../../../../.gitbook/assets/job conf 3.png" alt=""><figcaption></figcaption></figure>

* **Run Command**: specifies the command code to run the scan. \
  If you are using your own command, you should specify the _**/data/**_ directory to save the report in, so that it can be sent to the Appsec Portal.

<figure><img src="../../../../.gitbook/assets/job config 3.png" alt=""><figcaption></figcaption></figure>

* **Environment Variables**: environment variables to be used by the job are specified. \
  You can _**delete**_ a variable, _**mark**_ it _**as required**_, _**hide**_ it or _**add**_ additional environment variables if necessary

<figure><img src="../../../../.gitbook/assets/job conf 4.png" alt=""><figcaption></figcaption></figure>

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody><tr><td></td><td><img src="../../../../.gitbook/assets/image (14) (1) (1) (1).png" alt="" data-size="original"></td><td></td><td></td></tr><tr><td></td><td><img src="../../../../.gitbook/assets/image (15) (1) (1).png" alt="" data-size="original"></td><td></td><td></td></tr><tr><td></td><td><img src="../../../../.gitbook/assets/image (17) (1) (1).png" alt="" data-size="original"></td><td></td><td></td></tr></tbody></table>

{% hint style="warning" %}
Mandatory environment variables for each job type **Scanner**:\
<mark style="color:blue;">`REPORT_FILE_NAME`</mark> file name should send to the portal and \
<mark style="color:blue;">`SCAN_TYPE`</mark>[**importer**](../../../../appsec-portal/features/scanners/) (parser)  to process the report.
{% endhint %}
