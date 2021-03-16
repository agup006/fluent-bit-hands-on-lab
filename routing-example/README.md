# ROUTING EXAMPLE

Fluent Bit uses tags to route data when collected. In this example we will start out with the following configuration. This opens up an HTTP port on Fluent Bit to recieve any incoming data. The HTTP input plugin also allows us to dynamically route data via tags to the proper outputs. In this case we are matching all outputs, but we will change the output tag and show how data can be routed.

## Configuration

```
[SERVICE]
    flush        1
    log_level    info 
    parsers_file parsers.conf

[INPUT]
    name http
    port 9240

[OUTPUT]
    name stdout
    match *           
```
