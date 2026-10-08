# 🚀 Automação de Atendimento e Gestão de OS

> Sistema avançado de automação de fluxos conversacionais e gerenciamento de Ordens de Serviço (OS) integrado via webhooks, unindo mensageria omnichannel e banco de dados relacional.

---

## 🛠️ Tecnologias e Ferramentas Utilizadas
* **n8n:** Orquestração de fluxos, lógica condicional e tratamento de webhooks.
* **Chatwoot & API do WhatsApp:** Camada de atendimento omnichannel e mensageria.
* **Docker:** Self-hosting e gerenciamento de infraestrutura.
* **Banco de Dados (Firebird / SQL):** Consultas, persistência de dados, validação de status e controle de técnicos.

---

## 📋 Sobre o Projeto
Este repositório documenta a arquitetura de uma solução desenvolvida para otimizar operações de suporte técnico e atendimento ao cliente. O fluxo automatiza a recepção de mensagens, realiza validações em tempo real no banco de dados e direciona as demandas de forma inteligente.

### ✨ Principais Funcionalidades do Fluxo
* **Roteamento Inteligente:** Identifica automaticamente se o contato pertence a um cliente com atendimento em andamento ou se trata de uma nova demanda.
* **Cadastro de Ordens de Serviço (OS):** Subfluxo dedicado ao registro automatizado de chamados vinculados a técnicos específicos.
* **Consultas e Atualizações Dinâmicas:** Integração profunda com banco de dados utilizando nós condicionais (`If`, `Switch`) para validação de status e atualização de registros.
* **Encerramento de Chamados:** Tratamento automatizado para finalização de atendimentos e salvamento de histórico.

---

## 📊 Arquitetura do Fluxo (n8n)
Abaixo está a representação visual da lógica implementada no n8n para gerenciar as regras de negócio:

<div align="center">
  <!-- Dica: Você pode colocar um print limpo do seu fluxo na pasta do repo e linkar aqui -->
  <img src="fluxo-n8n.png" width="100%" alt="Fluxo n8n de Automação de Atendimento">
</div>

---

## 💡 Como Funciona
1. O cliente envia uma mensagem via WhatsApp.
2. O webhook aciona o fluxo orquestrado no **n8n**.
3. O sistema valida no banco de dados o histórico e o status atual do cliente.
4. Conforme a regra de negócio (seja cadastro de OS ou consulta de status), o fluxo executa as ações correspondentes e retorna a resposta integrada pelo **Chatwoot**.