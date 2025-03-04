# oracle-logstash-pipeline

[![CI](https://github.com/netways/oracle-logstash-pipeline/workflows/Logstash%20Syntax/badge.svg)](https://github.com/netways/oracle-logstash-pipeline/actions?query=workflow%3A%22Logstash+Syntax%22)

**Please do not use this for production, yet. This is a work in progress and we are yet in the process of finding potential problems with the ruleset. So do not rely on issues to check whether the rules are suitable for you or not**

Pipeline to parse Oracle logs

We built this pipeline for a special project which provided us with example logs. So the rules might not fit for your environment. And they are definitely extremely simplistic. Feel free to provide PRs for better parsing as long as your version can still work with the original one.

## Input and output ##

This pipeline has no input nor output. `.gitignore` includes `input.conf` and `output.conf` so you can use these files for your own input and output configuration.

Here are examples using a local Redis.
```
input {
  redis {
    host => "localhost"
    data_type => "list"
    key => "oracle"
  }
}

output {
  redis {
    host => "localhost"
    data_type => "list"
    key => "forwarder"
  }
}
```
