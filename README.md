# docker-solr

## Usage with mounted volume:

Prepare your Solr cores directory so that it looks like this:
../cores/core0/conf/schema.xml
../cores/core1/conf/schema.xml
../cores/coreX/conf/schema.xml
../cores/solr.xml

Then run:
$ docker run -v /absolute/path/to/cores/:/opt/solr/cores/solr/ -p "8983:8983" docker-solr

Then you can visit our browser at http://localhost:8983/solr/

Profit!
