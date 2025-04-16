# WindowsServerServiceStopped

## Meaning

A windows service with startup type set to "Automatic" has stopped.

## Impact

Stopped windows services might have different impacts depending on the specific server and components.

## Diagnosis

The alert indicates which service is not running.
You can find information to identify it under the `summary` label.

```console
 - host = someHost
...
 - summary = SomeService
```

Windows event logs is one of the first places to start the investigation, run the command below to see 
the last 10 system events

```console
Get-EventLog system -newest 10
```

## Mitigation

To mitigate this issue, you can follow the steps below and restart the failed service:

```console
Restart-Service SomeService
```

If restarting the service does not resolve the problem, continue the trobleshooting by restarting the VM:

```console
Restart-Computer
```

Further troubleshooting depends on the error reported by the service and there is no generic mitigation.

