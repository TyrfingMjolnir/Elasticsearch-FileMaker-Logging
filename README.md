# Elasticsearch-FileMaker-Logging
A simple example on how to log your users' FileMaker activity using Filebeat module and elasticsearch/ELK-stack

This FileMaker 12 file contains

2 tables
========
* settings, in which holds the host and port of the elasticsearch index
* es, in which holds a minimum set of data

4 Scripts
=========
* "Create ES index" in which is meant to create the index according to your FileMaker file's name
* "Update ES index" in which pushes a selection of data from the current record to elasticsearch
* "Operational script" Example of how to include "Update ES index" as the inital script step in your scripts
* "Display" failed attempt to harvest the button name

I hope this helps to get you started with logging how your FileMaker scripts work.

This is released in the aim of salus populi / the greater good, please use this for good.

Inspired in part by: http://joelabrahamsson.com/elasticsearch-101/
