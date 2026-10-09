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
<img src="https://skillicons.dev/icons?i=docker,nodejs,git,github,vscode&theme=dark"/>
</div>

* **n8n:** Orquestração de fluxos, lógica condicional e tratamento de webhooks.
* **Chatwoot & API do WhatsApp:** Camada de atendimento omnichannel e mensageria usando a CloudAPI como Tech Provider.
* **Docker & Docker Compose:** Self-hosting do Chatwoot e gerenciamento de infraestrutura.
* **Node.js (22 LTS):** Ambiente de execução para scripts de apoio e dependências.
* **Banco de Dados (Firebird / SQL):** Consultas, persistência de dados, validação de status e controle de técnicos.

---

## 📋 Sobre o Projeto
Este repositório documenta a arquitetura de uma solução desenvolvida para otimizar operações de suporte técnico e atendimento ao cliente. O fluxo automatiza a recepção de mensagens, realiza validações em tempo real no banco de dados e direciona as demandas de forma inteligente atribuindo os responsáveis e concluindo chamados através de controle condicional.

### ✨ Principais Funcionalidades do Fluxo
* **Roteamento Inteligente:** Identifica automaticamente se o contato pertence a uma empresa cadastrada no DB com atendimento em andamento ou se é uma nova demanda.
* **Cadastro de Ordens de Serviço (OS):** Subfluxo dedicado ao registro automatizado de chamados direcionados ao técnico correto.
* **Consultas e Atualizações Dinâmicas:** Integração profunda com banco de dados utilizando nós condicionais (`If`, `Switch`) para validação de status.
* **Encerramento de Chamados:** Tratamento automatizado para finalização de atendimentos e salvamento de histórico em tabelas de log.

---

## 📊 Arquitetura do Fluxo (n8n)
<div align="center">
  <img src="Imagens/FluxoCloudAPI.png" width="100%" alt="Fluxo n8n de Automação de Atendimento">
</div>

---

## 🚀 Guia de Instalação e Configuração (Passo a Passo)

Siga os passos abaixo para preparar o seu ambiente local ou servidor de homologação para rodar a stack completa.

### 1. Pré-requisitos
Certifique-se de ter as seguintes ferramentas instaladas em sua máquina/servidor:
* [Docker e Docker Compose](https://docs.docker.com/get-docker/)
* [Node.js (Versão 22 LTS ou superior)](https://nodejs.org/)
* Git

### 2. Clonando o Repositório
Abra o seu terminal e clone este repositório:
```bash
git clone [https://github.com/BrunoFreireDev/Automacao_de_Atendimento.git](https://github.com/BrunoFreireDev/Automacao_de_Atendimento.git)
cd Automacao_de_Atendimento
