# VMWareESXiHostPowerState

## Meaning
An ESXi host is powered down.

## Impact
VM's should have been moved to another ESXi host, but depending on how the ESXi host was powered down, it might have caused an VM restart.

## Diagnosis
Look at the monitoring to see if all VM's and services are healthy

## Mitigation


