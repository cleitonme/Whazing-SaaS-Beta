Antes de continuar fazer backup/snapshot da vps. Vericar com empresa contratada

Versão 2.8.14.3 - 25/03/25
- Melhoria cache mensagem enviada

Versão 2.8.14.3
 - integração simples wavoip para fazer chamadas somente
 - Ajustes dashboard by carlos eduardo
 - Aumentado limite envio arquivos 100MB e liberado enviar qualquer formato
 - Relatorios tickets exibi etiquetas

Versão 2.8.14.2

- Suporte mensagem agendadas Grupos
- Quebra linha chatinterno
- Disable botao enviar Atendimento até acabar envio
- Ajustes para melhor desempenho
- Renomeado menu empresas para SaaS
- Restriger exportar contatos somente para admin
- Encaminhamento mensagem, garantir saiu mesmo whatsapp e criar ticket usar mesma fila ticket original
- Enviar mensagem enter tela print

Versão 2.8.14.1

- Melhora sistemas mensagens, tentativa recuperar mensagens não compativeis
- No Canal whatsapp nova opção - Ignorar Grupos(necessário reniciar conexão)
- Webhook canal de ticket fechado - notifica quando fechado por inatividade

Versão 2.8.14

- Telegram
- Suporte integrações, chatbot interno, transcrição audio, avaliação

- ChatBot interno
- Receber arquivo bot recebe nome do arquivo 

Versão 2.8.13.1 - 13/03/2025

- Melhorias na validacao se usuario esta online
- Alterada sistema ligação - não enviar mensagem não aceita chamada caso já tenha sido enviado ultimas 24 horas - vamos ver como se comporta

Versão 2.8.13.1 - 12/03/2025

- Novo sistema conversão audios enviados e recebidos backend - tentar economizar processador
- Novo sistema download arquivos backend - tentar economizar processador
- Envio audio hub Instagram
- Atualização edição chatbot - Descidi liberar antes
- Troca versão alternativa baileys - pra ver se melhora algo - mas falta processamento é um grande problema - Mas tenho maquina 10 nucleos, nem toda empresa vps honesta e entrega realmente real, as vezes so são virtuais, e você compartilha nucleo com muitos usuarios.
- Fechar ticket ele retira integração - possibilitando apagar integração futuramente
- Listagem ticket pendente mostra foto - colocado botao aceitar e fechar ticket

Versão 2.8.13 - 08/03/2025

- Melhoria validação telefones sem 9 no whatsapp envio mensagens api para evitar falsos envios
- Removido filtro data adicionar campanha so dava confusão
- Verifica se foi enviada mensagem bloqueio chamada se tiver já não envia denovo

Versão 2.8.13 - 07/03/2025

- Erro CRM compartilhado - Exclusão de um contato de uma lane direto pela edição contatos não tava atualizando no crm

Versão 2.8.13 - 05/03/2025

- Erro CRM compartilhado - cadastro novos não listando lanes

Versão 2.8.13

- Mudança nos socket

- Usuarios
- Aviso já existe um cadastro com aquele email

- Tarefas
- Botão para vizualizar a tarefa completa

- Atualização cores mais alguns botões para seguir tema. Acredito com esse não ficou pontos sem ajustes

- Alteração mensagem Assas "Opss!!!!*\nNão localizamos nenhum boleto! Estamos transferindo para um *Atendente*!"

- Adicionado suporte proxy tipo socks nas configuração conexão whatsapp e possivel .env para todos whatsapp

- Chat interno
- bug - permitir envio mais de um arquivo

- Alterado logica rejeição chamadas

Versão 2.8.12

- Novo socket destina notificação mais especificas

- Novo Perfil Supervisor
- Pode acessar todos tickets/mensagens
- Pode apagar ticket individual
- Pode apagar anotação
- Acessar contatos mesmo estando desabilitado configurações
- Relatorios completos da dashboard
- Relatorios
- Painel Atendimento
- Editar e criar ChatBot, não pode apagar
- Whatsapp reniciar conexao, desconectar e ler qrcode novamente
- Acesso completo campanhas
- Acesso completo etiquetas
- Filas criar e editar
- Acesso completo edição equipes
- Usuarios acesso alterar, criar e editar todos usuarios exetos os admin, não pode escluir
- Agendamentos acesso total
- Despedida acesso total
- Tarefas acesso total
- Mensagens rapidas acesso total
- CRM acessa de outros usuarios

- CRM 
- bug - Com essa opcao ativa Separar lista de lane por usuario o admin nao conseguia acessar kanban outros usuarios
- bug - Lista contatos carregar crm admin consultar de outros usuarios
- Nova opção CRM compartilhado, todos usuarios compartilharam lanes.
- Atrelar chatbot na Lane sera acionado esse chatbot em novos tickets desse contato

- Atendimento
- bug - melhoria envio audio troca de Atendimento
- bug - troca mensagens 2 whatsapp cadastrados mesma empresa
- bug - anotação grande gera rolagem pagina dados contato
- bug - Listando grupos todos usuarios
- bug - Correção perca da cor canal
- PDF vizualizar nova ABA
- Badge seguir cor tema
- Ao clicar ticket com mensagens nao lida ele não sobe mais lista
- Clica esc fecha chat aberto
- Ao clicar ticket ja bem caixa input pronta digitar nao prescisa ir ate nela e clicar
- Ticket é de grupo desativar botão transferir bot
- Novos filtros admin
- Listar agendamentos no dados contato

- Filas/Integrações
- Usuario/Equipes
- Empresas
- Configurações
- bug - F5 perde cores

- Campanha
- bug - Informações corretas envio campanha
- bug - Atualizar pagina perde cores
- saudação - Ele considerava hora clicado programar envio montar saudação, entao caso horario fosse outro ele mandava errado.
- Aviso do risco de uso campanhas
- Filtro por lane da CRM
- Validação data para não ter problemas disparo e enviar de uma vez
- Validação contatos caso ja tenha enviado campanha que foi cancelada, enviar somente contatos que não foram enviados

- Relatorios
- bug - Filtro relatorio tickets filtra fila
- Novo relatorio por lane da CRM
- Novo relatorio de contator por carteira
- Ajustes seguir cor do tema

- Contatos
- bug - Correção modo dark adicionar contato
- Carregar agendamentos na edicao contatos

- Menu
- Renomeado menu filas e usuarios
- Api agrupado juntos canais

- Webhook
- Colocado no sistema de filas
- Novo Webhook Ticket transferido
- Novo Webhook Ticket fechado

- ChatBot
- bug - Se não tiver mensagem encerramento não encerava ticket
- Nova opção "fazer nada" realmente o que ta escrito não altera status chatbot para usar por exemplo na opção qualquer resposta e você nao quer avance as etapas. E nao exiba erro opção invalida

- Integrações ia
- bug - Melhor formatação resposta da ia para evitar espaço desnecessarios
- Colocado suporte, imagem, docx, pdf, xlxs

- Dashboard
- Charts seguir cor do tema

- Empresas
- bug - Escolha cores painel whitelabel
- Personalização mensagem limite arquivo
- Personalização mensagem não compativel com sistema

- Planos
- Exibição erro quando existe plano mesmo nome

- 2 Novas variaveis
- Saudação Espanhol:
   ```bash
   {{greetingEs}}
   ```
- Saudação Ingles:
   ```bash
   {{greetingEn}}
   ```
   
- Chamadas recebidas não abre mais ticket

- Hub Instagram
- Recebe comentarios na integração
- Fechar automaticamente Tickets de comentárioss
- Assinatura nao envia mais * negrito

- Conexão Whatsapp
- Alem de qrcode disponivel agora opção conectar com numero telefone

- Desativar mensagem temporario automatico foi retirado de grupos pois somente admin pode alterar isso

- Agendamento
- bug - Refatoriação logica para ver se não endoida mais
- Opção gravar audio

- Mensagens rapidas
- Opção gravar audio

- Segurança
- Single Login - Não possivel logar 2 dispositivos mesmo tempo - Opcional desabilitar no usuario

- Mudança badge notificação atendimento lista ticket com mensagens nao lidas abertos

Como atualizar

Use opção atualizar versão beta 11


