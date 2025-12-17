### Message Broker - RabbitMQ
![image](https://img.shields.io/badge/rabbitmq-%23FF6600.svg?&style=for-the-badge&logo=rabbitmq&logoColor=white)
![image](https://img.shields.io/badge/Docker%20Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)


RabbitMQ é um message broker amplamente utilizado para gerenciar a comunicação entre microserviços ou sistemas distribuídos. Ele atua como um intermediário que recebe, roteia e entrega mensagens entre produtores (quem envia) e consumidores (quem recebe).

**Componentes principais:**
- Exchanges: Responsáveis por rotear mensagens para as filas com base em regras (routing keys).
  - Direct: Roteia mensagens para filas específicas com base em uma routing key.
  - Fanout: Envia mensagens para todas as filas vinculadas, sem considerar a routing key.
- Queues (Filas):
  Armazenam mensagens até que sejam consumidas.
Cada fila pode ter um ou mais consumidores.
- Bindings: Conexões entre exchanges e filas, definindo como as mensagens são roteadas.




## 📦 Estrutura de Exchanges e Filas do message-broker

### 🔁 Exchange: `order.direct` (tipo: direct)
- 🔗 Routing Key: `order.created`
  - 📥 Queue: `order.created.queue`

- 🔗 Routing Key: `order.cancelled`
  - 📥 Queue: `order.cancelled.queue`

- 🔗 Routing Key: `order.delivered`
  - 📥 Queue: `order.delivered.queue`

- 🔗 Routing Key: `order.accepted`
  - 📥 Queue: `order.accepted.queue`

- 🔗 Routing Key: `order.in_route`
  - 📥 Queue: `order.in_route.queue`
  
### 📣 Exchange: `order.fanout` (tipo: fanout)
- 📥 Queue: `order.in_route.queue`
- 📥 Queue: `order.notification.queue`




### Inicialize o message broker
```bash
docker-compose up -d
```
*Adicione a rede `rabbitmq_net` nos serviços que irão se comunicar com o serviço do broker*
<br>
