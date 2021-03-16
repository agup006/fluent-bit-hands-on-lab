# ROUTING EXAMPLE

Fluent Bit uses tags to route data when collected. In this example we will start out with the following configuration. This opens up an HTTP port on Fluent Bit to recieve any incoming data. The HTTP input plugin also allows us to dynamically route data via tags to the proper outputs. In this case we are matching all outputs, but we will change the output tag and show how data can be routed.

We can also send data to the localhost by running the following command
`curl -d @app.log -XPOST -H "content-type: application/json" http://localhost:9240/app.log`

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
![image](https://user-images.githubusercontent.com/3642874/111241432-574ce300-85ba-11eb-81bb-42f75149048d.png)
