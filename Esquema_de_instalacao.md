ESQUEMAS DE CRIACAO DE CADA PROJETO DO N8N


# n8n instalacao vps via Easy Panel

# Instalaçao dos bancos de dados

- Postgres
- Redis

# Instalaçao do n8n

1. **Instale o editor**

```json
{
  "services": [
    {
      "type": "app",
      "data": {
        "projectName": "n8n_start",
        "serviceName": "n8n_start",
        "source": {
          "type": "image",
          "image": "n8nio/n8n:latest"
        },
        "domains": [
          {
            "host": "$(EASYPANEL_DOMAIN)",
            "port": 5678
          }
        ],
        "env": "N8N_ENCRYPTION_KEY=qwSYwLlijZOh+FaBHrK0tfGzxG6W/J4O",
         "deploy": {
                  "replicas": 1,
                  "command": "n8n start",
                  "zeroDowntime": true
        },
        "mounts": []
      }
    }
  ]
}
```

1. Instale o webhook

```json
{
  "services": [
    {
      "type": "app",
      "data": {
        "projectName": "n8n_webhook",
        "serviceName": "n8n_webhook",
        "source": {
          "type": "image",
          "image": "n8nio/n8n:latest"
        },
        "domains": [
          {
            "host": "$(EASYPANEL_DOMAIN)",
            "port": 5678
          }
        ],
        "env": "N8N_ENCRYPTION_KEY=qwSYwLlijZOh+FaBHrK0tfGzxG6W/J4O",
         "deploy": {
          "replicas": 1,
          "command": "n8n webhook",
          "zeroDowntime": true
        },
        "mounts": []
      }
    }
  ]
}
```

1. Instale o worker

```json
{
  "services": [
    {
      "type": "app",
      "data": {
        "projectName": "n8n_worker",
        "serviceName": "n8n_worker",
        "source": {
          "type": "image",
          "image": "n8nio/n8n:latest"
        },
        "domains": [
          {
            "host": "$(EASYPANEL_DOMAIN)",
            "port": 5678
          }
        ],
        "env": "N8N_ENCRYPTION_KEY=qwSYwLlijZOh+FaBHrK0tfGzxG6W/J4O",
         "deploy": {
          "replicas": 1,
          "command": "n8n worker --concurrency=10",
          "zeroDowntime": true
        },
        
        "mounts": []
      }
    }
  ]
}
```


```
