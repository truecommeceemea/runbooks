# LinuxHostOutOfMemory

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
 - alertname = LinuxHostHighCpuLoad
...
 - host = SomeHost:1234
```

You can use follow the steps below to list processes that are using the most memory. 
After you determine the specific process causing high memory utilization, you can troubleshoot that application.

```console
ps -eo pid,ppid,%mem,%cpu,cmd --sort=-%mem | head
```

## Mitigation

Mitigation depends on the application and there is no generic one, but in most cases an restart should help.

In order to restart linux and return to a healthy status, follow the steps below:

```console
sudo reboot 
```

Confirm that the memory usage has returned to normal values.
