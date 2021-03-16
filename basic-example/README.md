# BASIC ROUTING
In this configuration we will showcase how to collect and push data through Fluent Bit.

We use the CPU input plugin to collect metrics from the Linux Operating System, then route to standard output

## Configuration
```
# Visualized https://link.calyptia.com/ryt
[SERVICE]
    flush        1 
    daemon       Off
    log_level    info
    parsers_file parsers.conf
    plugins_file plugins.conf
    http_server  Off
    http_listen  0.0.0.0
    http_port    2020

[INPUT]
    name cpu
    tag  cpu.local
    interval_sec 1

[OUTPUT]
    name  stdout
    match *
```
![image](https://user-images.githubusercontent.com/3642874/111241062-9af31d00-85b9-11eb-8eba-2a9d9622ac11.png)
