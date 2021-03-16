# Fluent Bit Hands On Lab
This repository contains examples that showcase Fluent Bit examples, and how to get started. Fluent Bit is a Cloud Native Computing Project (CNCF) as a sub-project under the Fluentd project. More information can be found at https://fluentbit.io

In addition, to using examples found in documentation, this repository also makes use of [Calyptia](https://config.calyptia.com) to visualize the data pipelines, as well as the following repository to generate fake logs (https://github.com/kiritbasu/Fake-Apache-Log-Generator)

List of examples in this repository
1. Basic example
2. Routing example
3. Enrichment example
4. Stream Processing examples
  * SELECT
  * AGGREGATION
  * TIMESERIES PREDICTION
  * GROUP BY MESSAGES


# How to run
You can run most of these examples on the command-line with Fluent Bit. We will use td-agent-bit packaged version
1. Clone this repository
2. Move all .conf files to /etc/td-agent-bit/
3. Run td-agent-bit from the command-line
4. /opt/td-agent-bit/bin/td-agent-bit -c <INSERT EXAMPLE FILE PATH>


