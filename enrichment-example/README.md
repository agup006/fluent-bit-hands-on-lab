# ENRICHMENT EXAMPLE
In this example we will enirch data that is incoming from fluent bit. We will first read apache logs that are found in /var/log/apache then for the `host` field we will initiate a lookup against the MaxMind Database to understand which country the request is coming from. From here we will route the results to standard output

## Configuration
```
# Visualized https://link.calyptia.com/21k
[SERVICE]
    flush        1
    log_level    info 
    parsers_file parsers.conf

[INPUT]
    name              tail
    path              /var/log/apache/*.log
    tag               apache
    parser            apache
    read_from_head    true

[FILTER]
    name geoip2
    match apache
    database /home/anugup/GeoLite2-City.mmdb
    lookup_key host
    Record country host %{country.names.en}

[OUTPUT]
    name stdout
    format json
    match *
```
![image](https://user-images.githubusercontent.com/3642874/111241879-3d5fd000-85bb-11eb-9e62-911e7f153548.png)
