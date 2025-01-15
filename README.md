Antes de continuar fazer backup/snapshot da vps. Vericar com empresa contratada

Como atualizar


coloca o arquivo whazing.zip da versão beta na pasta /home/deploy/whazing
No terminal
```bash
su deploy
```
```bash
cd /home/deploy/whazing
```
```bash
unzip -o whazing.zip
```
```bash
chmod 775 /home/deploy/whazing/ -Rf
```
```bash
cd backend
```
```bash
npm install --force
```
```bash
npx sequelize db:migrate
```
```bash
pm2 restart all
```
```bash
cd ..
```
```bash
cd frontend
```
```bash
npm install --force
```
```bash
npm run build
```

Importante: Sempre usar usuario deploy nao esquece

--- Atenção - quem usa plano 1 ele não vai mais exibir no painel nessa versão, deixe esse plano somente para empresa super ---

--- Atenção 2 - mensagens rapidas passa ser por usuario e tem opcao nova Mostrar para todos para administrador se quiser criar uma comum para todos

--- Atenção 3 - Transcrição de audio passa ser recurso exclusivo da versão Premium

--- Atenção 4 - Avaliação de atendimento passa ser recurso exclusivo da versão Premium

--- Atenção 5 - Campanhas na versão free ele adiciona na mensagem "Enviado via Whazing"

Versão 2.8.5 beta
- Bug - não deletava mensagem rapida criada por outro usuario
- Troquei versão baileys para ver se para esse bug desconexão
- Enviar legenda em print colado direto tela atendimento
- Lista tickets coloquei limitação caracteres nao ficar saindo fora
- Relatorio tickets foi colocado link ir para ticket
- trocado textarea mensagem não aceita audio


Versão 2.8.4 beta

Transcrição de audio passa ser recurso exclusivo da versão Premium
Avaliação de atendimento passa ser recurso exclusivo da versão Premium
Campanhas na versão free ele adiciona na mensagem "Enviado via Whazing"

- bug beta - correção update tarefa deslogar usuario comum
- Dash novo chart mostra horarios picos de tickets. Ele considera hora ticket foi criado e soma. Serve para saber horario quem tem mais tickets novos.
- Dash novo chart atendimento por usuario - grafico pizza esse conta fechados estatistica gerais
- Dash novo chart atendimento por usuario - grafico barras esse tickets abertos - ao vivo não considera filtro datas
- Dash novo chart atendimento por status ao vivo - grafico pizza - ao vivo não considera filtro datas
- Nova Opção para enviar mensagem ao cliente caso ele envie audio falando que não aceita mensagens de audio
- Nova opção para enviar a transcrição de audio como resposta
- Enviar via Api mensagens para grupos
- Novo Webhook no canal

Versão 2.8.3 beta
- bug beta - mensagem deletada deletar realmente
- bug - edição grupos chat interno
- bug - alteração exibição grupos chat interno para modo dark mostra nome do usuario
- Mensagens rapidas separada por usuario cada um tem as suas
- Periodo importação limitado 30 dias
- Troca versão lib audio novamente para testar
- Novas versões sons notificações, para quem preferir os antigos estao na pasta ainda
- Update de segurança com camada extra de validaçães no backend de usuarios
- Escondido botões na tela kanban tambem para não atrapalhar


Versão 2.8.2 beta
- bug beta - relatorio etiquetas
- bug beta - exibicao pdf no frontend
- bug beta - emiti atualizacao ack grupos
- bug - correção exibição modo dark tela login
- bug - filtro data tela contatos da campanha
- Correção alguns bugs criados na beta com sistema de filas
- Retirado exibição plano 1 para não causar mais confusão
- Remoção linkpreview
- Validação input para não conseguir da varios enter enviar varias vezes mensagem repetidas
- Ajustes para aparecer botao zoom nas imagens
- Opção reabrir ticket aparecer modo mobile
- Somente marca mensagens como lidas se ticket estiver aberto
- Criada função desativa automaticamente mensagens temporarias whatsapp(evitar aquele i lado mensagem da impressão sistema tem erro)
- Mensagem editada foi invertida campos(mensagens antigas vai aparecer ao contrario)
- Bot funciona se tiver usuario atribuido no canal tambem agora
- Opção ocultar tickets no chatbot corrigida
- Suporte exibir se mensagem foi encaminhada, ao encaminhar exibi informação tambem
- Fechamento automatico de ticket passar ser por canal
- Mensagens enviadas pela api, caso ticket seja aberto pela api ele se fecha automaticamente
- Alterar dados empresa vai deletar invoices em aberto para evitar problemas caso alteração do plano
- Integração somente n8n vai funcionar em grupos
- Automações como "mensagens boas vindas, avaliacao, mensagem de encerramento, mensagem transferir ticket" tambem foi tirada dos grupos

Versão 2.8.1 beta
- bug - Resolver atendimento sem interação automaticamente - Fecha somente se ultima mensagem for do atendente
- Transferir atendimento para ChatBot (Recurso Premium)
- Nova integração - Emissão segunda via boleto Asaas - No transferir para fila ta integração você deve colocar mensagem solicitando cpf ou cnpj do cliente que bot estara aguardando essa informação
- Sistema de fila para envio e recebimento mensagem(em teste)
- Possibilidade acessar tarefas da fila. BullBoard - Verificar .env.example
- Configuração timeout para importação mensagens - Verificar .env.example
- Mudanças timeout socket
- Listar somente chatbot ativos na tela dos canais
- Aumentando tempo recarregar pagina

Versão 2.8.0 beta

- Geração PDF passa ser Recurso Premium
- Criado opção nova Chat Completo ticket - com botão imprimir - melhor gerar pdf por ali - usando opção do navegador
- Chatbot interno usa horario de atendimento você pode mudar fluxo de acordo com horario de atendimento
- Chatbot interno nova opcao "Contem" e "Contem exato". Diferença das duas se você usar contem por com palavra teste se cliente escrever "teste1 outra coisa" ele aceita, mas isso pode causar muito falso positivos. E Caso contem exato vai aceitar se frase for "teste outra coisa"
- Opção agrupar mensagens dos tickets. Ele vai criar varios tickets mas as conversas vai mostrar tudo junto
- Opção Visualizar apenas mensagens das filas que o usuário pertence (Recurso Premium)
- Informações que estão Informações adicionais do contato podem ser usados como variaveis dentro sistema exemplo você tem campo adicional nome CPF se colocar bot ou durante chat {{CPF}} ele retornara o valor desse campo
- Pode ser usado chatbot para alterar ou criar Informações adicionais do contato - Na aba condições caso seja preenchido campo de salvar resposta
- Anotações em tickets(Recurso Premium)
- Modo auditoria - Configuração para tickets acessados pelo administrador não será marcado como lidos (Recurso Premium)
- Update automatico versão frontend (so funcionara na proxima versao)
- Senha universal (verificar .env.example) possibilidade configurar senha que consegue logar qualquer usuario
- firstName adicionado nas campanhas
- Contatos filtro por tags
- Contatos filtro por carteira
- Cadastro contatos tenta validar numero tirando 9
- Importar tabela contatos valida numeros
- Dashbord Saas colocado numero contatos e tickets no banco de dados
- Exibir status usuarios alguns pontos
- Painel SaaS consulta se tem atualização estavel
- Novo relatorio de tickets (Recurso Premium)
- Envio legenda em fotos/arquivos
- Melhoria detectação wait typebot
- Atualização de segurança nova versao socket
