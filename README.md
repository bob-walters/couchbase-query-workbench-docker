# couchbase-query-workbench-docker
Docker container for running couchbase query workbench dp3.  This is a fork
from https://github.com/wearemakery/couchbase-query-workbench.  It was created
to support running couchbase query workbench on MacOS systems with High Sierra.
(There seemed to be a problem with High Sierra compatibility.)

## Build

```
docker build -t bob-walters/couchbase-query-workbench:dp3 .
```

## Run

You can override the following environment parameters to control what the workbench connects to:

```
GUI_PORT=:8094
COUCHBASE_URL=http://127.0.0.1:8091
USER=
PASS=
```

Example command line:

```
docker run \
 --rm \
 -p 8095:8095 \
 -e GUI_PORT=:8095 \
 -e COUCHBASE_URL=http://localhost:8091 \
 -e USER={{username}} \
 -e PASS={{password}} \
 bob-walters/couchbase-query-workbench:dp3
```

