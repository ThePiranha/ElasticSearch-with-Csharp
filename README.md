### What is this repository for? ###

* This repository contain sample code how to connect ElasticSearch with Visual Studio and use C# to search data in ES

What is Elasticsearch?
----------------------
http://www.elasticsearch.org/

ElasticSearch is a distributed RESTful search engine built for the cloud. Features include:

* Distributed and Highly Available Search Engine.
	* Each index is fully sharded with a configurable number of shards.
	* Each shard can have one or more replicas.
	* Read / Search operations performed on either one of the replica shard.
* Multi Tenant with Multi Types.
	* Support for more than one index.
	* Support for more than one type per index.
	* Index level configuration (number of shards, index storage, …).
* Various set of APIs
	* HTTP RESTful API
	* Native Java API.
	* All APIs perform automatic node operation rerouting.
* Document oriented
	* No need for upfront schema definition.
	* Schema can be defined per type for customization of the indexing process.
* Reliable, Asynchronous Write Behind for long term persistency.
* (Near) Real Time Search.
* Built on top of Lucene
	* Each shard is a fully functional Lucene index
	* All the power of Lucene easily exposed through simple configuration / plugins.
* Per operation consistency
	* Single document level operations are atomic, consistent, isolated and durable.
* Open Source under Apache 2 License.

Installing Elasticsearch
------------------------
### Installing Elastic Search on a Windows server
* Pre-requisites: 
	* Java Runtime Environment (JRE) http://www.oracle.com/technetwork/java/javase/downloads/index.html
	* After installing JRE, do yourself a favor and set the JAVA___HOME environment variable
		* My Computer -> Properties -> Advanced tab -> Environment variables button
		* Under System Variables, click Add New
		* Name: JAVA___HOME
		* Path: c:\progra~1\Java\jre7
		* Assumes Java JRE is installed at c:\program files\Java\jre[X]
* You can download the Elasticsearch runtime from the Elasticsearch website and follow the standard installation instructions (it's really quite simple)
* OR, if you'd like the Elasticsearch engine to run as a Windows service, you can download an installer from here: http://ruilopes.com/elasticsearch-setup/
	* Basically the installer just unzips the Elasticsearch package, then creates a Windows service wrapping the engine
	* Install to [DRIVE]:\Elasticsearch (avoid installing to the Program Files directory to help avoid UAC issues)
	* An Elasticsearch service will be created, but you may need to start the service manually (Administrative tools -> Services) and set it to startup automatically
* Confirm Elasticsearch is running by browsing to: http://localhost:9200/_cluster/health
	* If you receive a JSON response with a property named "status" that has a value of "green" or "yellow", all systems are go.
	* By default, Elasticsearch listens on port 9200.

	
### Install a web-based management tool for Elastic Search
* I like the Kibana for cluster/node/index monitoring - https://www.elastic.co/products/kibana	
* I also like the Sense plugin for Google Chrome for testing queries - https://chrome.google.com/webstore/detail/sense/doinijnbnggojdlcjifpdckfokbbfpbo
* Another great client elasticsearch-head also good for monitoring cluster - https://mobz.github.io/elasticsearch-head/
* Several other options/tools available here: http://www.elasticsearch.org/guide/clients/
	* Scroll to the "Health and Performance Monitoring" and "Front Ends" sections

# ElasticSearch-with-Csharp
ElasticSearch with C#

Example project for using Elasticsearch with C#. This is a autosearch feature demonstration in Elasticsearch using C#.NET. User cansearch any name by typing its first character. Example for searching user "Abby" jusy type A and it will list all the name that has A in it.

# Getting Started
Download NEST package using the below command and then run the program. You can learn more about Elasticsearch.NET & NEST [here](https://github.com/elastic/elasticsearch-net).


```
<code>PM> Install-Package NEST</code>
```

# Sample Data
You could use the attached data and insert them or you can use your own data. If you use you own data please change the index name in the Form1.cs code to your index name and type to your type name. Also you need to update the getter and setter.
