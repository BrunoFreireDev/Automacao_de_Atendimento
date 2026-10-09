```markdown
# ⚙️ Etapa 3: Orquestração no n8n e Integração com o ERP (Firebird)

Esta etapa abrange a configuração da lógica de atendimento, o tratamento de webhooks vindos do Chatwoot e a comunicação direta com o banco de dados Firebird do ERP.

---

## 🛠️ Pré-requisitos de Ambiente
* **Node.js:** Versão 22 LTS (ou superior) instalada para gerenciar o n8n globalmente (versão `v2.35.7+`).
* **Cloudflare Tunnels:** Utilizado para expor os webhooks do n8n de forma segura para a internet, permitindo que o Chatwoot se comunique com o servidor local.
* **Nó da Comunidade:** Instalação do pacote `n8n-nodes-banco-firebird` para permitir consultas e manipulações dinâmicas no SGBD Firebird.

---

## 🔄 Fluxo de Dados e Automação
1. **Recepção de Webhook:** O Chatwoot dispara eventos de novas mensagens ou alteração de status para o n8n.
2. **Roteamento Inteligente:** O n8n processa a mensagem, executa queries SQL para identificar se o cliente já possui cadastro ou Ordens de Serviço (OS) ativas.
3. **Abertura/Encerramento de Chamados:** Com base na interação, o fluxo automatiza o registro da OS no ERP ou dispara o encerramento da conversa quando marcada como "Resolvida" no Chatwoot.