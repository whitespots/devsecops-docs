# 🗒️ Release notes

**release\_v25.06.1**

```
- More entrypoints for microservices
```

**release\_v25.03.1**

```
- Added timeout
- Added dns
```

**release\_v24.11.2 (latest)**

```
- Added endpoint for running bulk audits
- Small fixes and improvements
```

**release\_v24.10.2**

```
- Reworked jobs settings
- Improved deployment stability 
- Added vendor provided settings
- Minor fixes and improvements
```

**release\_v24.07.2**

1. Minor bug fixes and improvements <mark style="color:blue;">**`UPDATE`**</mark>

**release\_v24.06.3**

1. Changes in fixtures

#### release\_v24.05.1&#x20;

1. **Added audits**: Now sends `audit_id` in the report for better tracking and reference. <mark style="color:green;">**`NEW`**</mark>
2. **Added cloud account**: Introduced support for cloud accounts as a new asset type. <mark style="color:green;">**`NEW`**</mark>

#### release\_v24.04.1&#x20;

1. **Improved filtering**: The ability to filter jobs by scanner name and status has been added. <mark style="color:green;">**`NEW`**</mark>

#### release\_v24.01.1&#x20;

1. **Pipeline Termination Option**: Introduced the capability to terminate all pipelines, providing enhanced control over pipeline management <mark style="color:green;">**`NEW`**</mark>
2. **Workers Count Display:** Added a display feature for workers count, providing visibility into the current number of active workers <mark style="color:green;">**`NEW`**</mark>

#### release\_v23.12.4&#x20;

1. Added branch from Code Downloader to send reports
2. Add allow\_failure: bool setting. If False - non-zero exit code from job will kill pipeline

#### release\_v23.12.3&#x20;

1. New Scanners: Checkov, Prowler AWS, Terrascan
2. Small fixes

**release\_v23.12.1**

1. Small fixes
2. New Scanners added
3. Masking variables values in logs

#### release\_v23.11.2

1. Auditor Schedule added
2. Fixed sorting by date
