# Elasticsearch-FileMaker-Logging
A simple example on how to log your users' FileMaker activity using Filebeat module and elasticsearch/ELK-stack

This FileMaker 12 file contains

2 tables
========
* settings, in which holds the host, port, username, and password of the elasticsearch index
* es, in which holds a minimum set of data

4 Scripts
=========
* "Create ES index" in which is meant to create the index according to your FileMaker file's name
* "Update ES index" in which pushes a selection of data from the current record to elasticsearch
* "Operational script" Example of how to include "Update ES index" as the inital script step in your scripts
* "Display" failed attempt to harvest the button name

I hope this helps to get you started with logging how your FileMaker scripts work.

This is released in the aim of salus populi / the greater good, please use this for good. If you have to go evil, go Chromium.

Inspired in part by: http://joelabrahamsson.com/elasticsearch-101/

This is a project adopting the logs of FileMaker 17 Server to the filebeat log shipper for elasticsearch aka elk-stack

The purpose of this module is to give you as the user the ability to browse your FileMaker 17 Server logs visually using kibana, or elasticsearch in other ways to analyze your logs.

# Current status is: Access.log is ready for testing.

# Some notes

http://help.filemaker.com/app/answers/detail/a_id/6551/~/tracking-activity-in-log-files-in-filemaker-server
https://www.elastic.co/guide/en/beats/devguide/current/filebeat-modules-devguide.html

To reset the grok:
```Sh
curl -XDELETE http://localhost:9200/_ingest/pipeline/filebeat-5.6.2--filemaker-pipeline
```

Note to self, the major difference between logstash and beats are: ```\\``` and ```\\\``` respectively.

This piece of software was written by Arne Rolf Heier and Gjermund Gusland Thorsen; even though we claim the copyright this software is free for you to use and modify as long as the original authors are credited. This piece of software comes with no warranty what so ever. Use it at your own risk.

Thanks to "Ask any questions you'd like" at Elastic{on} Tour Stockholm 2018; for helping me find a way to validate my groks live; using ```"POST _ingest/pipeline/_simulate"```
