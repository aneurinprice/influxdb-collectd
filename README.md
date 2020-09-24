## Auto-Mirrored from Gitlab to Github and to My Registry

## Please make Pull/Merge Requests on my Gitlab, Issues can be raised anywhere 

### Available on my [Gitlab](https://gitlab.nyeprice.space/moby/docker-icingaweb2) 

### Available on [Github](https://github.com/aneurinprice/docker-icingaweb2) 

### Available on [My Registry](https://registry.nyeprice.space) 


## Docker Image ##
`registry.nyeprice.space/influxdb-collectd/influxdb-collectd:latest`

## Current Issues: ##
 
  

Is based on _influxdb:latest_

It's pretty self explanitory. This is a fork of the Official Influxdb Docker Image that comes pre-loaded with the Collectd  Typeset. This will still require all the config from influxdb. Because their documentation (at the time of writing this) is terrible, I have included a snippet that should work in most situations:

```
[meta]
  dir = "/var/lib/influxdb/meta"

[data]
  dir = "/var/lib/influxdb/data"
  engine = "tsm1"
  wal-dir = "/var/lib/influxdb/wal"

[[collectd]]
  enabled = true
  bind-address = ":25826" # the bind address
  database = "collectd" # Name of the database that will be written to
  retention-policy = ""
  batch-size = 5000 # will flush if this many points get buffered
  batch-pending = 10 # number of batches that may be pending in memory
  batch-timeout = "10s"
  read-buffer = 0 # UDP read buffer size, 0 means to use OS default
  typesdb = "/usr/share/collectd/types.db"
```


For Instructions how to use this image, please see [ The Official Influxdb Docker Documentation](https://hub.docker.com/_/influxdb)





## Example command: ##
  - `docker run -d -p 25826:25826 registry.nyeprice.space/influxdb-collectd/influxdb-collectd:latest`