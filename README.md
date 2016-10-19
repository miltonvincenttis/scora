###### (c) copyright 2016 - Milton Vincenttis
---
## CORA: Core Architecture
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
* Mensageria
* Persistencia

#### Communicação:
  * API Gateway - Public Open Source [kong | tyk.io]
  * RESTful API
    * Vertx + EasyRest + Atmosphere

#### Segurança
* Registro:
   * usr+pwd
   * Two-way
* Autenticação:
  * JWTdh | OAuth
* Autorização:
  * Spring Security
* Criptografia:
  * Canal Seguro: TLS (certificados)
  * Ponta-a-Ponta: Noise | Signal

#### Mensageria
* NATS
  * Queue
  * Pub/Sub

#### Persistencia
* SQL
  * MySQL
* NOSQL
  * Cassandra

## Infraestrutura:

#### Serviços em Cloud:
* Public OpenSource API Gateway:
  * kong | tyk.io
* Armazenagem de arquivos:
  * AWS-S3 - Simple Storage
  * Google Cloud Storage/Bigtable/Datastore
* Hospedagem web app:
  * AWS-EC2 - Elastic Compute Cloud
  * GCP - Google Cloud Platform:
    * App Engine
