# 🚀 Automação de Atendimento e Gestão de OS

> Sistema avançado de automação de fluxos conversacionais e gerenciamento de Ordens de Serviço (OS) integrado via webhooks, unindo mensageria omnichannel e banco de dados relacional.

---

## 🛠️ Tecnologias e Ferramentas Utilizadas
* **n8n:** Orquestração de fluxos, lógica condicional e tratamento de webhooks.
* **Chatwoot & API do WhatsApp:** Camada de atendimento omnichannel e mensageria usando a CloudAPI como Tech Provider.
* **Docker:** Self-hosting do Chatwoot e gerenciamento de infraestrutura para funcionamento e atendimento.
* **Banco de Dados (Firebird / SQL):** Consultas, persistência de dados, validação de status e controle de técnicos.

---

## 📋 Sobre o Projeto
Este repositório documenta a arquitetura de uma solução desenvolvida para otimizar operações de suporte técnico e atendimento ao cliente. O fluxo automatiza a recepção de mensagens, realiza validações em tempo real no banco de dados e direciona as demandas de forma inteligente atribuindo os responsáveis e até mesmo concluidno demandas através do controle condicional do fluxo.

### ✨ Principais Funcionalidades do Fluxo
* **Roteamento Inteligente:** Identifica automaticamente se o contato pertence a um contato cadastrado no DB relacionado a uma empresa e com atendimento em andamento ou se trata de uma nova demanda.
* **Cadastro de Ordens de Serviço (OS):** Subfluxo dedicado ao registro automatizado de chamados direcionados condicionalmente ao tecnico correto conforme atendimento.
* **Consultas e Atualizações Dinâmicas:** Integração profunda com banco de dados utilizando nós condicionais (`If`, `Switch`) para validação de status e atualização de registros dentro do DB e tabelas do próprio fluxo.
* **Encerramento de Chamados:** Tratamento automatizado para finalização de atendimentos e salvamento de histórico nas tabelas do fluxo como uma forma de Logs para controle e consultas posteriores.

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
2. O Chatwoot recebe a informação recebida pela CloudAPI da meta e redireciona para o webhook acionando o fluxo orquestrado no **n8n**.
3. O fluxo valida no banco de dados se o número que entrou em contato consta no cadastro de alguma empresa no ERP.
4. Se o número que entrou em contato está cadastrado, então uma mensagem automática é enviada no whats com saudações e pedindo ao cliente como podemos o ajudar.
   Caso o número que entrou em contato seja novo uma ocorrência é cadastrada no sistema avisando aos técnicos que devem cadastrar o novo número como contato no cadastro da empresa.
5. Após concluir o envio das mensagens uma tabela de controle é atualizada avisando que o cliente já recebeu as saudações e agora está aguardando o atendimento de um técnico da equipe.
6. Assim que um técnico manda a primeira mensagem o fluxo novamente é acionado seguindo o subfluxo que cadastra uma OS (Chamado) no ERP, dando assim inicio ao atendimento, já preenchendo as informações de para qual empresa é o chamado, qual o técnico responsável e o inicio extao do atendimento.
7. Quando o técnico marca a conversa do chatwoot como "resolvida" então o chatwoot manda uma atualização para o webhook dando inicio ao subfluxo que vai identificar a OS e cliente, fazendo a conclusão da OS.