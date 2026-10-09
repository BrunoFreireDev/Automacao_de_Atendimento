# 🛡️ Guia Prático: Como se Tornar um Tech Provider da Meta (WhatsApp Cloud API)

Este manual tem como objetivo orientar desenvolvedores e empresas sobre o processo prático e os cuidados necessários para obter a homologação como **Tech Provider** junto à Meta, permitindo a coexistência fluida entre o aplicativo móvel do WhatsApp e plataformas omnichannel como o Chatwoot.

---

## ⏱️ Expectativa de Prazo e Planejamento
* **Tempo médio de aprovação:** 15 a 20 dias úteis.
* **Aviso de tranquilidade:** O processo realmente **demora**. Fique tranquilo: o tempo de espera prolongado **não significa que você foi reprovado** — é apenas o tempo padrão de fila de análise da Meta.
* **Recomendação:** Inicie este processo com antecedência em relação à infraestrutura técnica, pois a validação exige análises que dependem do cumprimento rigoroso das diretrizes da Meta.

---

## 🧭 Passo a Passo para Homologação

### 1. Preparação da Conta do Facebook (Evitando Filtros Antifraude)
A Meta possui filtros de segurança extremamente rígidos para contas novas. Para evitar bloqueios automáticos:
* **Idade da Conta:** A conta do Facebook não pode ser recém-criada. O ideal é que tenha pelo menos uma semana de existência.
* **Conta Humanizada:** A conta precisa demonstrar atividade real de um usuário comum (como seguir e curtir páginas de adoção de pets para simular comportamento orgânico).
* **Perfil Completo:** Deixe todas as informações de contato da conta devidamente preenchidas.
* **Página Comercial:** Crie uma Página do Facebook para representar a sua empresa. *Nota:* Caso você já tenha criado uma página comercial, o próprio Facebook encarrega-se de criar automaticamente o Portfólio Empresarial (Business Portfolio) vinculado a ela. 

> ⚠️ **ALERTA CRÍTICO DE SEGURANÇA:** **Em hipótese alguma altere a senha da sua conta do Facebook** logo antes ou durante o processo de configuração. O sistema de segurança da Meta interpreta a troca de credenciais associada a atividades de desenvolvimento como sinal de conta comprometida, resultando em bloqueio imediato e permanente.

### 2. Acesso ao Meta for Developers e Configuração do App
* Com a conta aquecida e o portfólio pronto, acesse o [Meta for Developers](https://developers.facebook.com/) e faça login.
* Crie um novo aplicativo com o caso de uso voltado para **WhatsApp Business** e vincule-o ao portfólio da empresa.
* **Escopos Essenciais:** Ao solicitar as funções e permissões do aplicativo, **solicite apenas as funções essenciais de controle da conta business e de mensagens**. Manter o escopo enxuto facilita muito a aprovação com um único vídeo.
* **Número de Teste:** Utilize um número avulso (um chip ou linha com a qual você não se importe muito no dia a dia) para configurar a API nesta fase inicial.

### 3. Verificação da Empresa (O Pulo do Gato: Validação por Domínio)
* **Evite Documentos Físicos:** Não tente validar enviando contratos sociais ou comprovantes de endereço tradicionais; os filtros costumam recusar por mínimos detalhes.
* **Validação por Domínio:** **Utilize a comprovação de vínculo empresarial através de um domínio web próprio.** É um processo infinitamente mais rápido, automatizado e certeiro para obter o status de negócio verificado.

### 4. Gravação do Vídeo de Demonstração (Screencast)
Quando a Meta solicitar a comprovação de uso da API por vídeo, siga esta estrutura utilizando o [OBS Studio](https://obsproject.com/pt-br/download):
* **Cenário Preparado:** Tenha o **Chatwoot** integrado à Cloud API usando o número cadastrado, e o aplicativo do **WhatsApp Business** (ou normal) aberto.
* **Demonstração Prática:** Divida a tela exibindo o Chatwoot em uma metade e o WhatsApp na outra:
  1. Envie uma mensagem do seu WhatsApp pessoal para o número da API.
  2. Mostre o Chatwoot recebendo essa mensagem em tempo real.
  3. Responda a mensagem diretamente de dentro do painel do Chatwoot.
  4. Mostre a resposta chegando no seu WhatsApp.
* **Objetivo:** Comprove visualmente que você está conversando com você mesmo, evidenciando a intenção legítima de uso da ferramenta.

### 5. O Momento Certo de Publicar
* **Mantenha em Desenvolvimento:** Durante toda a fase de testes e gravação para validação como Tech Provider, **não coloque o seu aplicativo em produção**. 
* Deixe para tirar o app da fase de desenvolvimento **somente após** concluir integralmente todo o processo de aprovação e homologação.

### 6. A Chegada ao Pote de Ouro: Embedded Signup no Chatwoot
Após a aprovação formal do seu aplicativo como Tech Provider na Meta:
* **Publicação do App:** Agora sim, altere o status do seu aplicativo da Meta para **Produção**.
* **Configuração da Caixa de Entrada:** No painel do Chatwoot, prossiga com a configuração da caixa de entrada utilizando o **Embedded Signup (Cadastro Incorporado)**.
* 💡 **Dica de Ouro do Navegador:** Para realizar o login e o fluxo do Embedded Signup no Chatwoot, **utilize um navegador limpo, totalmente sem bloqueadores de anúncios (AdBlockers)** ou extensões restritivas. Isso evita que extensões bloqueiem o pop-up da Meta (que gerencia permissões, credenciais e gera o QR code a ser lido pelo celular cadastrado no WhatsApp Business), permitindo concluir o cadastro com sucesso absoluto.

---