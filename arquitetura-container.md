###### (c) Copyright 2016 - Milton Vincenttis
---
### Arquitetura Base

#### Camada dockerizada:
* Communication
	* vertx/vertx3:3.3.3 
* Messaging
	* nats:0.9.4
	* rabbitmq:3.6.6
* Security
	* keycloak
* Persistence
	* cassandra:3.9
	* mysql:5.17
* Logging
	* Fluentd
	* Logstash
	* Kibana
* Monitoring
	* Prometheus
