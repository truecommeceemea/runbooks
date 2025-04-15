# VMWareDatastoreOutOfSpace

## Meaning

This alert is based the space used in a datastore. It fires if the current usage is above a certain threshold

## Impact

A filesystem running completely full is obviously very bad for any process in need to write to the filesystem. But even before a filesystem runs completely full, performance is usually degrading.

## Diagnosis

Study the recent trends of filesystem usage on a dashboard. Sometimes a periodic pattern of writing and cleaning up can trick the linear prediction into a false alert.

Use the usual OS tools to investigate what directories are the worst and/or recent offenders.

Is this some irregular condition, e.g. a process fails to clean up behind itself, or is this organic growth?


## Mitigation
