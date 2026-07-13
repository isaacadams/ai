library: https://ollama.com/search

```bash
docker compose exec ollama ollama list
docker compose exec ollama ollama pull smollm2:135m
docker compose exec ollama ollama pull deepseek-r1
```

another possible way to deploy ollama w/ gbu enabled processing?

```yaml
version: '3.3'
services:
  ollama-webui:
    ports:
      - '3000:8080'
    container_name: ollama-webui
    image: ollamawebui/ollama-webui
  ollama:
    volumes:
      - './ollama:/root/.ollama'
    ports:
      - '11434:11434'
    environment:
      - 'OLLAMA_ORIGINS=*'
    container_name: ollama
    image: ollama/ollama
    deploy:
      resources:
        reservations:
          devices:
            - driver: nvidia
              count: 1
              capabilities: [gpu]
```
