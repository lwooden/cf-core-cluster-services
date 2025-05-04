logging adheres to the original fluentbit/kubernetes spec

Original Fluentbit Configuration
- splits log groups by workload/namespace
- log streams are organized by pod name

this is much cleaner and easier to reason about than the new specification

log_group_template    /aws/eks/fluentbit-cloudwatch/workload/$kubernetes['namespace_name']
log_stream_template   $kubernetes['pod_name'].$kubernetes['container_name']
