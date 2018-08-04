# geoipWithELK

To try this use case, I would suggest to use ELK6.x. I have tested with below versions of ELK stack,

logstash-6.3.1,

elasticsearch-6.3.1,

kibana-6.3.1-linux-x86_64


Follow the below steps, to test geoip with ELK,

clone the project by, git clone https://github.com/mdrilwan/geoipWithELK.git

Before starting logstash, update the elasticsearch mappings to store coordinates as geo_point type, by following the below steps,

Start Elasticsearch

Then run the below commands in your terminal,

cd geoipWithELK/geoip 

curl --header "content-type: application/JSON" -XPUT 'http://localhost:9200/_template/geoip' -d@geoiptemplate.json

Update the path of input file in logstash configuration file geoip.conf and start logstash

Once data is indexed in elasticsearch, you can try tilemap visualization in kibana

For details, visit http://rilwan.in/get-location-from-geoip-using-elk/
