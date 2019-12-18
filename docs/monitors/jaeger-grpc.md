<!--- GENERATED BY gomplate from scripts/docs/templates/monitor-page.md.tmpl --->

# jaeger-grpc

Monitor Type: `jaeger-grpc` ([Source](https://github.com/signalfx/signalfx-agent/tree/master/pkg/monitors/jaegergrpc))

**Accepts Endpoints**: No

**Multiple Instances Allowed**: **No**

## Overview

Runs a GRPC server that listens for Jaeger trace batches
and forwards them to SignalFx (or the configured ingest host in the
`writer` section of the agent config).  By default, the server listens on
localhost port 14250 but can be configured to anything.


## Configuration

To activate this monitor in the Smart Agent, add the following to your
agent config:

```
monitors:  # All monitor config goes under this key
 - type: jaeger-grpc
   ...  # Additional config
```

**For a list of monitor options that are common to all monitors, see [Common
Configuration](../monitor-config.md#common-configuration).**


| Config option | Required | Type | Description |
| --- | --- | --- | --- |
| `listenAddress` | no | `string` | The host:port on which to listen for traces. (**default:** `0.0.0.0:14250`) |
| `tls` | no | `object (see below)` | TLS are optional tls credential settings to configure the GRPC server with |


The **nested** `tls` config object has the following fields:

| Config option | Required | Type | Description |
| --- | --- | --- | --- |
| `certFile` | no | `string` | The cert file to use for tls |
| `keyFile` | no | `string` | The key file to use for tls |



