# WindowsServerMemoryUsage

## Meaning

A  process is causing high memory utilization in a VM

## Impact

High memory utilization might indicate an software error or a system that is under unusual high load.
It might not be an problem, but if it continues over a longer priod of time, it could be an symptom of an application
having problems.

## Diagnosis

The alert indicates which server is having High memory utilization
You can find information to identify it under the `host` label.

```console
 - alertname = WindowsServerMemoryUsage
...
 - host = SomeHost:1234
```

You can use Powershell, or Task Manager from windows to see the processes that are using the most memory. 
After you determine the specific process causing high memory, you can troubleshoot that application.

To see the top 1 process memory usage, open powershell as administrator and do:

```console
Get-Process | Sort-Object -Descending WS | select -first 1 | select -ExpandProperty ProcessName
```

## Mitigation

Mitigation depends on the application and there is no generic one, but in most cases an restart should help.

In order to restart windows and return to a healthy status, open powershell (as administrator) and follow the steps below:

```console
Restart-Computer -ComputerName localhost -Force
```

Confirm that the memory usage has returned to normal values.
