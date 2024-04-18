# Whitespots Portal

Whitespots Portal Scanner provides the ability for users to submit their own data to Appsec Portal for further processing and management. To do this, the importer needs to provide a list of dictionaries in the following format:

<pre><code><strong>[
</strong><strong>    {
</strong>        name : “str“,
        severity : “str”,
        description : “str”,
        file_path : “str”,
        line : int,
        vulnerable_url : “str”,
        dependency : “str”
    }
]
</code></pre>

This tool provides flexibility and allows users to submit their data for further analytics and security improvements using Appsec Portal.
