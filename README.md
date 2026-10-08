<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1e293b,55:0f172a,100:020617&height=180&section=header&text=Automa%C3%A7%C3%A3o%20de%20Atendimento&fontSize=34&fontColor=38bdf8&animation=fadeIn&fontAlignY=40" width="100%"/>

<img src="https://readme-typing-svg.herokuapp.com?font=JetBrains+Mono&weight=600&size=16&duration=3200&pause=900&color=38bdf8&center=true&vCenter=true&width=750&lines=Orquestra%C3%A7%C3%A3o+de+fluxos+com+n8n+e+Chatwoot;Integra%C3%A7%C3%A3o+Omnichannel+via+WhatsApp+CloudAPI;Automa%C3%A7%C3%A3o+de+Ordens+de+Servi%C3%A7o+(OS)+com+Banco+de+Dados"/>

<br>

<a href="https://www.linkedin.com/in/bruno-freire-log"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/></a> <a href="https://github.com/BrunoFreireDev"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/></a>

<br><br>

</div>

---

## 🛠️ Tecnologias e Ferramentas Utilizadas

<div align="center">
<img src="https://skillicons.dev/icons?i=docker,git,github,vscode&theme=dark"/>
</div>

* **n8n:** Orquestração de fluxos, lógica condicional e tratamento de webhooks.
* **Chatwoot & API do WhatsApp:** Camada de atendimento omnichannel e mensageria usando a CloudAPI como Tech Provider.
* **Docker:** Self-hosting do Chatwoot e gerenciamento de infraestrutura para funcionamento e atendimento.
* **Banco de Dados (Firebird / SQL):** Consultas, persistência de dados, validação de status e controle de técnicos.

---

## 📋 Sobre o Projeto
Este repositório documenta a arquitetura de uma solução desenvolvida para otimizar operações de suporte técnico e atendimento ao cliente. O fluxo automatiza a recepção de mensagens, realiza validações em tempo real no banco de dados e direciona as demandas de forma inteligente atribuindo os responsáveis e até mesmo concluindo demandas através do controle condicional do fluxo.

### ✨ Principais Funcionalidades do Fluxo
* **Roteamento Inteligente:** Identifica automaticamente se o contato pertence a um contato cadastrado no DB relacionado a uma empresa e com atendimento em andamento ou se trata de uma nova demanda.
* **Cadastro de Ordens de Serviço (OS):** Subfluxo dedicado ao registro automatizado de chamados direcionados condicionalmente ao técnico correto conforme atendimento.
* **Consultas e Atualizações Dinâmicas:** Integração profunda com banco de dados utilizando nós condicionais (`If`, `Switch`) para validação de status e atualização de registros dentro do DB e tabelas do próprio fluxo.
* **Encerramento de Chamados:** Tratamento automatizado para finalização de atendimentos e salvamento de histórico nas tabelas do fluxo como uma forma de Logs para controle e consultas posteriores.

---

## 📊 Arquitetura do Fluxo (n8n)
Abaixo está a representação visual da lógica implementada no n8n para gerenciar as regras de negócio:

<div align="center">
  <img src="Imagens/FluxoCloudAPI.png" width="100%" alt="Fluxo n8n de Automação de Atendimento">
</div>

---

## 💡 Como Funciona

<table>
<tr>
<td width="100%" valign="top">

1. **Recepção:** O cliente envia uma mensagem via WhatsApp.
2. **Webhook:** O Chatwoot recebe a informação repassada pela CloudAPI da Meta e redireciona para o webhook acionando o fluxo orquestrado no **n8n**.
3. **Validação:** O fluxo valida no banco de dados se o número que entrou em contato consta no cadastro de alguma empresa no ERP.
4. **Triagem de Contato:** 
   * Se o número **está cadastrado**, uma mensagem automática é enviada no WhatsApp com saudações e perguntando ao cliente como podemos ajudar.
   * Se o número for **novo**, uma ocorrência é cadastrada no sistema avisando aos técnicos que devem cadastrar o novo número como contato no cadastro da empresa.
5. **Controle de Estado:** Após concluir o envio das mensagens, uma tabela de controle é atualizada avisando que o cliente já recebeu as saudações e agora está aguardando o atendimento de um técnico da equipe.
6. **Abertura de OS:** Assim que um técnico manda a primeira mensagem, o fluxo novamente é acionado seguindo o subfluxo que cadastra uma OS (Chamado) no ERP, dando início ao atendimento e preenchendo as informações da empresa, o técnico responsável e o horário exato de início.
7. **Encerramento:** Quando o técnico marca a conversa do Chatwoot como "resolvida", o Chatwoot envia uma atualização para o webhook dando início ao subfluxo que vai identificar a OS e o cliente, fazendo a conclusão da OS.

</td>
</tr>
</table>

---

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1e293b,55:0f172a,100:020617&height=80&section=footer" width="100%"/>
</div>