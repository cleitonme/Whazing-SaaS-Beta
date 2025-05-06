# ⚙️ **Configurações do WHAZING**

Bem-vindo às configurações do sistema WHAZING!  
Aqui você encontrará todas as opções de personalização para adaptar o atendimento às necessidades da sua operação.

---

## 📋 Resumo Rápido

| Seção | Descrição |
|:--|:--|
| [Configurações Gerais](#configurações-gerais) | Ajustes principais do sistema |
| [Atendimento e Tickets](#atendimento-e-tickets) | Gerenciamento de tickets, pendências e visibilidade |
| [Controle de Acesso](#controle-de-acesso) | Restrições e permissões de usuários |
| [CRM/Kanban](#crmkanban) | Configurações específicas do módulo CRM e Kanban |

---

## ⚙️ Configurações Gerais

- 🔄 **Agrupar mensagens de tickets diferentes**  
  Exibe o histórico de mensagens anteriores no mesmo ticket. Ideal para consultas rápidas, mas pode ser desativado para manter setores separados.

- 📂 **Visualizar apenas mensagens das filas que o usuário pertence**  
  Usuários veem apenas as conversas das filas em que estão atribuídos, aumentando a privacidade.

- 🕵️ **Administrador e Supervisores em modo auditoria**  
  Acesso sem marcar conversas como lidas.

- 🔒 **Não visualizar tickets privados atribuídos a outros usuários**  
  Protege tickets privados de serem acessados por outros usuários da fila.

- 🤖 **Não visualizar tickets em atendimento pelo ChatBot**  
  Esconde os tickets ainda em tratamento pelo chatbot interno.

- 🧩 **Habilitar guia de atendimento de Chatbots**  
  Cria uma guia específica para visualizar apenas atendimentos em chatbot.

- 👻 **Ocultar guias de atendimento sem tickets**  
  Esconde guias sem tickets ativos.

- 🛰️ **Exibir status das conexões na tela de atendimento**  
  Mostra o status dos canais (WhatsApp, Instagram, etc.) em tempo real.

- 📵 **Ocultar número de telefone para usuários**  
  Protege a privacidade dos números de contato.

---

## 🎫 Atendimento e Tickets

- 📋 **Somente administradores podem acessar a lista de contatos**  
  Restringe a tela de contatos apenas para administradores.

- 🧳 **Forçar atendimento via Carteira**  
  Encaminha automaticamente contatos para seus responsáveis (carteiras).

- 👥 **Listar apenas contatos da carteira do usuário**  
  Exibe somente os contatos da carteira atribuída ao usuário.

- 🔄 **Fluxo ativo para o Bot de atendimento**  
  Define o fluxo padrão para o atendimento automatizado.

- 🚫 **Ignorar mensagens de grupo**  
  Não recebe mensagens de grupos (opcionalmente habilitável no canal).

- 🔔 **Habilitar notificações de grupos**  
  Permite notificações de novas mensagens em grupos.

- 📞 **Recusar chamadas no WhatsApp**  
  Bloqueia chamadas de voz via WhatsApp.

- 💬 **Mensagem ao rejeitar ligação**  
  Define a resposta automática ao cliente após rejeição de chamada.

- ✍️ **Usuários poderão desativar a assinatura das mensagens**  
  Permite usuários removerem assinatura automática nas respostas.

- 👀 **Usuários podem espiar tickets**  
  Visualizar mensagens sem assumir o atendimento.

- ♻️ **Usuários podem reabrir tickets**  
  Permite reabertura de tickets fechados (atenção para mensagens fora de ordem).

- ⏳ **Voltar tickets para pendentes se o atendente demorar a responder**  
  Tickets voltam automaticamente para a fila de pendentes após tempo sem resposta.

- ⏰ **Tempo em minutos para voltar aos pendentes**  
  Define o intervalo de tempo para essa ação automática.

- 📤 **Máximo de vezes para enviar mensagem de fora do horário de atendimento**  
  Controle da quantidade de alertas enviados ao cliente.

- 🧮 **Limitar quantidade de tickets carregados**  
  Define quantos tickets abertos, pendentes e fechados serão carregados na tela para otimizar performance.

- 🕵️ **Lista de tickets fechados exibir apenas o último ticket do contato**  
  Mostra apenas o ticket mais recente de cada contato para facilitar o histórico.

---

## 🔐 Controle de Acesso

- 🛡️ **Compartilhar CRM entre todos os usuários**  
  Todos os usuários acessam as informações do CRM.

- 🧍‍♂️ **Listar contatos de tickets sem usuários no CRM**  
  Exibe contatos de tickets sem responsáveis atribuídos.

- 📁 **Listar contatos com tickets fechados**  
  Exibe contatos que já tiveram tickets encerrados (pode deixar o CRM mais lento).

- 🚶‍♂️ **Separar lista de lanes por usuário**  
  Cada usuário terá seu próprio CRM independente (quando o CRM não for compartilhado).

- 📜 **Listar contatos que não possuem tickets**  
  Exibe todos os contatos, mesmo os que nunca abriram tickets (pode afetar performance em bases grandes).

---

# 📌 Notas Finais

- 📉 Bases muito grandes podem afetar a performance do CRM e da tela de atendimento. Ajuste os limites conforme sua estrutura.
- ⚠️ Cuidado ao reabrir tickets antigos: pode gerar confusão no histórico das mensagens.
- 🔄 Atualize as configurações com base no seu modelo de operação para garantir segurança, privacidade e eficiência.