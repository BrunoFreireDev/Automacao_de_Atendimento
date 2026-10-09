# 🛡️ Guia Prático: Como se Tornar um Tech Provider da Meta (WhatsApp Cloud API)

Este manual orienta desenvolvedores sobre o processo prático e os cuidados burocráticos necessários para obter a homologação como **Tech Provider** junto à Meta, permitindo a coexistência entre o aplicativo móvel do WhatsApp e plataformas omnichannel como o Chatwoot.

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
* **Conta Humanizada:** A conta precisa demonstrar atividade real de um usuário comum (como seguir e curtir páginas para simular comportamento orgânico).
* **Perfil Completo:** Deixe todas as informações de contato da conta devidamente preenchidas.
* **Página Comercial:** Crie uma Página do Facebook para representar a sua empresa. *Nota:* Caso tenha criado uma página comercial, o próprio Facebook cria automaticamente o Portfólio Empresarial (Business Portfolio) vinculado a ela. 

> ⚠️ **ALERTA CRÍTICO DE SEGURANÇA:** **Em hipótese alguma altere a senha da sua conta do Facebook** logo antes ou durante o processo de configuração. O sistema de segurança da Meta interpreta a troca de credenciais associada a atividades de desenvolvimento como sinal de conta comprometida, resultando em bloqueio permanente.

### 2. Acesso ao Meta for Developers e Configuração do App
* Acesse o [Meta for Developers](https://developers.facebook.com/) e faça login com sua conta aquecida.
* Crie um novo aplicativo com o caso de uso voltado para **WhatsApp Business** e vincule-o ao portfólio da empresa.
* **Escopos Essenciais:** Ao solicitar as funções e permissões do aplicativo, **solicite apenas as funções essenciais de controle da conta business e de mensagens**. Manter o escopo enxuto facilita a aprovação com um único vídeo.
* **Número de Teste:** Utilize um número avulso para configurar a API nesta fase inicial.

### 3. Verificação da Empresa (O Pulo do Gato: Validação por Domínio)
* **Evite Documentos Físicos:** Não tente validar enviando contratos sociais ou comprovantes de endereço tradicionais; os filtros costumam recusar por mínimos detalhes.
* **Validação por Domínio:** **Utilize a comprovação de vínculo empresarial através de um domínio web próprio.** É um processo infinitamente mais rápido, automatizado e certeiro para obter o status de negócio verificado.

### 4. Gravação do Vídeo de Demonstração (Screencast)
Quando a Meta solicitar a comprovação de uso da API por vídeo, utilize ferramentas como o [OBS Studio](https://obsproject.com/pt-br/download):
* **Cenário Preparado:** Tenha o Chatwoot integrado à Cloud API usando o número cadastrado, e o WhatsApp Business aberto.
* **Demonstração Prática:** Divida a tela exibindo o Chatwoot em uma metade e o WhatsApp na outra:
  1. Envie uma mensagem do seu WhatsApp pessoal para o número da API.
  2. Mostre o Chatwoot recebendo essa mensagem em tempo real.
  3. Responda a mensagem diretamente de dentro do painel do Chatwoot.
  4. Mostre a resposta chegando no seu WhatsApp (comprove visualmente que você está conversando com você mesmo).

### 5. O Momento Certo de Publicar
* **Mantenha em Desenvolvimento:** Durante toda a fase de testes e gravação para validação como Tech Provider, **não coloque o seu aplicativo em produção**. 
* Deixe para tirar o app da fase de desenvolvimento **somente após** concluir todo o processo de aprovação e homologação.