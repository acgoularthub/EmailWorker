### Projeto para envio de e-mails com workers

**Objetivo**
Criar um sistema com back e frontend que emule envios de emails, implementando proxy reverso e alguns outros sistemas de segurança, além de praticar a escalabilidade da aplicação com auxílio do docker.

**Frontend**: HTML em cima do nginx 1.13, co uma rede própria (web), o nginx também será responsável pelo proxy reverso.

**Banco de dados**: Postgres:9.6

**Workers**: Feitos em Python 3.6

**Queue**: Redis 3.2 para fazer a fila funcionar.

**Aplicação**: Escrita em python 3.6, será responsável por enfileirar as mensagens.

A escalabilidade do sistema não é automática, depende de desinarmos a criação de novos workers, que no caso é feito durante a execução do `docker-compose`. Usa-se o comando a seguir para criar os workers:

```
# docker-compose up -d --scale nome-do-worker=n
```
onde você passa o nome do worker e o numero de workers que você irá necessitar.