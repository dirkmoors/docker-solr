# docker-solr

## Usage with mounted volume:

1. Prepare your Solr cores directory so that it looks like this:
```
../cores/core0/conf/schema.xml
../cores/core1/conf/schema.xml
../cores/coreX/conf/schema.xml
../cores/solr.xml
```

2. Then run:
```bash
$ docker run -v /absolute/path/to/cores/:/opt/solr/cores/solr/ -p "8983:8983" docker-solr
```

3. Then you can visit our browser at http://localhost:8983/solr/

4. Profit!
