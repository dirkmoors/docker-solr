# docker-solr

## Usage with mounted volume:

* Prepare your Solr cores directory so that it looks like this (be aware that you'll probably need more then just 'schema.xml'):
```
../cores/core0/conf/schema.xml
../cores/core1/conf/schema.xml
../cores/coreX/conf/schema.xml
../cores/solr.xml
```

* And configure your ../cores/solr.xml to look like this:
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<solr persistent="false">
  <cores adminPath="/admin/cores" host="${host:}" hostPort="${jetty.port:8983}" hostContext="${hostContext:solr}">
    <core name="core0" instanceDir="core0" />
    <core name="core1" instanceDir="core1" />
    <core name="coreX" instanceDir="coreX" />
        
    <shardHandlerFactory name="shardHandlerFactory" class="HttpShardHandlerFactory">
      <str name="urlScheme">${urlScheme:}</str>
    </shardHandlerFactory>
  </cores>        
</solr>
```

* Then run:
```bash
$ docker run -v /absolute/path/to/cores/:/opt/solr/config/cores/ -p "8983:8983" dirkmoors/solr
```

* Then you can visit our browser at http://localhost:8983/solr/

* Profit!
