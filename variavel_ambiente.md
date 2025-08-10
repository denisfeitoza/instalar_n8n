#######################################

Configurações Gerais

#######################################

NODE_FUNCTION_ALLOW_EXTERNAL=moment,lodash,moment-with-locales

EXECUTIONS_DATA_PRUNE=true
EXECUTIONS_DATA_MAX_AGE=336

GENERIC_TIMEZONE=America/Sao_Paulo
TZ=America/Sao_Paulo

EXECUTIONS_MODE=queue

N8N_ENCRYPTION_KEY=qwSYwLlijZOh+FaBHrK0tfGzxG6W/J4O

N8N_HOST=n8n-n8n-start.txepo8.easypanel.host
N8N_EDITOR_BASE_URL=https://n8n-n8n-start.ALTERE.easypanel.host
N8N_PROTOCOL=https
NODE_ENV=production
WEBHOOK_URL=https://n8n-n8n-start.ALTERE.easypanel.host

N8N_REINSTALL_MISSING_PACKAGES=true

#######################################

Configuração de E-mail

#######################################

N8N_EMAIL_MODE=smtp

N8N_SMTP_HOST=smtp.gmail.com
N8N_SMTP_PORT=465
N8N_SMTP_USER=denisfeitozadejesus@gmail.com
N8N_SMTP_PASS=alexandre101020
N8N_SMTP_SENDER="Denis denisfeitozadejesus@gmail.com"
N8N_SMTP_SSL=true

#######################################

Configuração do Banco de Dados

#######################################

DB_TYPE=postgresdb
DB_POSTGRESDB_DATABASE=database
DB_POSTGRESDB_HOST=n8n_postgres
DB_POSTGRESDB_PORT=5432
DB_POSTGRESDB_USER=postgres
DB_POSTGRESDB_PASSWORD=ALTERE

#######################################

Configuração do Redis

#######################################

QUEUE_BULL_REDIS_HOST=n8n_redis
QUEUE_BULL_REDIS_PORT=6379
QUEUE_BULL_REDIS_DB=2
QUEUE_BULL_REDIS_USER=default
QUEUE_BULL_REDIS_PASSWORD=ALETERE

#######################################

Configurações para processamento de vídeos

#######################################

N8N_ALLOW_EXTERNAL_PROCESS_EXECUTION=true
N8N_PROCESS_TIMEOUT=900000
N8N_BINARY_DATA_SIZE_LIMIT=50
N8N_BINARY_DATA_TTL=3600
N8N_USER_FOLDER=/tmp/n8n

#######################################

Configuração do RabbitMQ (modo fila)

#######################################

N8N_QUEUE_MODE=rabbitmq
N8N_QUEUE_RABBITMQ_HOST=n8n-rabbitmq.ALTERE.easypanel.host
N8N_QUEUE_RABBITMQ_PORT=5672
N8N_QUEUE_RABBITMQ_USER=n8n
N8N_QUEUE_RABBITMQ_PASSWORD=n8n
N8N_QUEUE_RABBITMQ_VHOST=/
