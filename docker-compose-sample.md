# Docker compose sample.

Voici un exemple de Docker compose sample pour la production. Ce docker compose est utilise pour la prod (a mettre sur le serveur de prod).

```
version: '3.9'

services:
  api:
    image: '124507821/api-agendax:v1.92'
    container_name: agendax_api
    env_file:
      - ./.env.prod
    ports:
      - "3005:3005"

  client_app_1:
    image: '124507821/admin-agendax:v1.5'
    container_name: agendax_admin
    env_file:
      - ./.env.production
    ports:
      - "5173:80"

  client_app_2:
    image: '124507821/client-agendax:v1.6'
    container_name: agendax_client
    env_file:
      - ./.env.production
    ports:
      - "5174:80"

  agendax_redis:
    image: 'redis:6.2-alpine'
    container_name: agendax_redis
    restart: always
    ports:
      - "6379:6379"
    command: redis-server --save 20 1 --loglevel warning --requirepass eYVX7EwVmmxKPCDmwMtyKVge8oLd2t81
    volumes:
      - redis:/data
    networks:
      - app-network

volumes:
  #db:
    #driver: local
  redis:

networks:
  app-network:
    driver: bridge
```