# objects-analytics-elk-config

Configuration files required to build own Nutanix Objects Analytics Dashboard

Link to related blog which has information on Objetcs Notifications and setting up the Analytics Dashboard - https://www.linkedin.com/pulse/draft/AgGQjnTsgM0hdQAAAXPhy1J3yWvMxCI__Yrps9VtnHI0fjcLFdNQuJANfSxFCb9pgfptNmE 

Link to video on Analytcis Dashboard and Notifications - https://youtu.be/qB96VjUzzEQ 

## Logstash Configuration

1. Download the logstash configuration - logstash.conf
2. Modify the Elasticsearch cluster’s IP address in the configuration file
3. Restart logstash with the specified configuration file to start parsing the notification logs
4. Once logstash starts check on kibana API if the index *objects-notification* is created 

## Kibana Configuration

1. Download the kibana configuration file - objsdash.ndjson
2. Import the downloaded kibana configuration file -> On Kibana 7.7 -> Management -> Saved Objects -> Import Saved Objects 
3. Once the configuration file is imported, the saved objects should list the dashboard, the corresponding visualizations and the index-pattern which were created
   You can click on the Objects Analytics Dashboard to launch it 
4. You can also click on the Discover Tab to search and drill down to specific events. Whenever we need to search based on specific field, we need to use the field which ends with  .keyword 
5. For example if you want to search for specific events - EventType field - you need to use -  n.EventType.keyword 
