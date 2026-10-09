# 💬 Etapa 2: Instalação do Chatwoot e Integração com a CloudAPI

Esta etapa cobre a implantação da camada omnichannel (Chatwoot) e a conclusão do processo de integração após a aprovação do Tech Provider na Meta.

---

## 🐳 1. Subindo o Chatwoot via Docker
Certifique-se de manter a versão estável recomendada (`v4.17.0` ou superior) no seu `docker-compose.yml` e suba os containers da aplicação:
```bash
docker compose up -d