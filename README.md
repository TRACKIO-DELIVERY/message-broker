### Message Broker - RabbitMQ
![image](https://img.shields.io/badge/rabbitmq-%23FF6600.svg?&style=for-the-badge&logo=rabbitmq&logoColor=white)
![image](https://img.shields.io/badge/Docker%20Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)

Aplicação de mensageria para gerenciamento da comunicação entre microserviços do TrackIO



### Crie a rede utilizada na conexão com o container do rabbit
```bash
docker network create rabbitmq_net
```
** Adicione essa rede nos serviços que irão se comunicar com o serviço do broker <br>



## 📦 Estrutura de Exchanges e Filas (RabbitMQ)

### 🔁 Exchange: `order.direct` (tipo: direct)
- 🔗 Routing Key: `order.created`
  - 📥 Queue: `order.created.queue`

- 🔗 Routing Key: `order.cancelled`
  - 📥 Queue: `order.cancelled.queue`

- 🔗 Routing Key: `order.delivered`
  - 📥 Queue: `order.delivered.queue`

- 🔗 Routing Key: `order.accepted`
  - 📥 Queue: `order.accepted.queue`


### 📣 Exchange: `order.fanout` (tipo: fanout)
- 📥 Queue: `order.in_route.queue`
- 📥 Queue: `order.notification.queue`
