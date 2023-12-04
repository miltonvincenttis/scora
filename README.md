###### Copyright (c) 2016 - Milton Vincenttis
---
## Scalable Core Architecture (in progress)
Visionando uma Arquitetura Escalável.
Desenhar e implementar uma arquitetura base para Apps escaláveis.

## Escalabilidade
O nível de serviço deve se manter, e deve aumentar ou diminuir conforme a demanda, deve ser elástico.

## Tolerância a falhas
Um serviço prestado por um App não pode falhar, sair do ar, deixar de atender seus usuários. Deve prover redundância sem qualquer ponto de falha.

## Alta Performance
O tempo que cada usuário de um App leva pra ser atendido pelo App deve ser o menor possível, e esse tempo deve ser constante, esteja o App atendendo a 2 usuários ou a 1 bilhão de usuários simultaneamente. Batalhar por baixissima latência.

## Segurança
O usuário de um App deve poder se registrar, se autenticar, e utilizar na App somente aquilo que tem permissão.
Troca de dados sensíveis entre App client/App server deve ser criptografada ponta-a-ponta, ou usar canal seguro.

 * Autenticação
 * Autorização
 * Criptografia


## Baixo Custo
A Arquitetura é construída e executada utilizando-se **OSS**.

---

### Arquitetura baseada em MicroServiços
#### :: Camadas básicas

* Communicação
* Segurança
* Persistencia
* Observabilidade

#### Comunicação:
  * RESTful API, BFF, API Gateway
  * Mensageria (BUS)
    * RabbitMQ, Kafka
  
#### Segurança
* Autenticação:
 * JWS token
 * eventualmente OAuth2

* Autorização:
 * RBAC
 * eventualmente OAuth2

* Criptografia:
   * Canal Seguro: TLS (certificados)
   * Ponta-a-Ponta: Noise | Signal
	
#### Persistencia
* SQL
  * Postgres
* NOSQL
  * Postgres + jsonb (columns)

#### Observabilidade
* Metrics    	(Quarkus)
* Tracing	(Quarkus)
* Logging	(Quarkus)
  
## Infraestrutura:

#### Serviços em Cloud:

** AWS - Amazon Web Services **
  * S3  - Simple Storage Services: arquivos
  * EC2 - Elastic Compute Cloud: app
  * Route53 - API Gateway

** GCP - Google Cloud Platform: **
  * AppEngine
  * Storage
  * Bigtable
  * Datastore
  
---

#### Serviços em ambiente de Desenvolvimento:
  * Persistence
	* MySQL 5.7.16
	* Cassandra
	  
  * Messaging
	* RabbitMQ
	* ZeroMQ
	* NATS
  
  * Cache
	* Redis
	* Hazelcast
