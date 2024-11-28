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

Versão 2.7.6 beta
- Bug versao beta - Campanha erro adicionar contatos
- Bug versão free - Listas filas nao atualizava corretamente versão free
- Bug - Contatos sem numeros fazendo da erro campanhas e outros relatorios
- Bug - Mais uma alteração filtros lista de atendimento para ver se melhora comportamento(não retornava ticket sem fila e atribuido ao usuario)
- Bug - Melhorias formatação textos vindo Typebot
- Delay 10s enceramento ticket pelo chatbot para garantir mensagem de enceramento seja entregue antes de fechar ticket
- Opção selecionar usuario online e offline hoje não tem uma utilidade decidir tirar para futuro talvez usar ela para alguma coisa util
- Mudança de cores padrões pelo painel SaaS
- Campanhas podem ser deletadas qualquer momento retirado validações
- Configuração para whazing não baixar mensagens que você envia por fora da prataforma(exemplo disparo pelo wasender, se cliente responder vai abrir o ticket)

Versão 2.7.5 beta

### Teve varias mudanças no kanban verificar configuração ####

- bug - problema formatação numeros causando erros conexoes hub - já que são contatos sem numeros
- Filtro na tela de agendamento pela data que foi agendado
- Chat interno aceita colar print no input
- Filtro LANE de contatos no KANBAN
- Edição lane kanban direto no contato
- Edição lane kanban direto na tela de antendimento
- Nas configurações tem 3 opções novas kanban uma para mostrar contatos tickets fechados, outra mostrar contatos sem fila atribuida e para deixar lanes ser compartilhados entre os usuarios e somente admin pode criar, editar e apagar lista de lanes.
- Tela atendimento mostra descrição informações adicionais tambem
- Tela atendimento mostra Valor negociação caso ela exista
- Opção "Reabrir tickets anteriores" alterada quando for criar ticket pela aba contatos tambem vai buscar tickets anteriores e reabre o mesmo


Versão 2.7.4 beta

- bug - importar historico de mensagem
- bug - tela atendimento modo celular não abre Dados de contato
- bug - Aumentado timeout para envio arquivos maiores edição de mensagens rapidas
- bug - Arquivos enviados pelo typebot não era exibidos corretamente no frontend
- bug - Enviar outros arquivos alem audio mostrava como gravando
- bug - Verificar nome do canal antes de cadastrar um HUB
- bug - Mensagens agendadas envia mesmo ticket fechado agora
- Cache grupos para melhor um pouco desempenho
- Validação se email já existe antes cadastrar nova empresa
- Validação se whatsapp já existe antes cadastrar nova empresa no teste
- Update versão varios pacotes como sequelize e outros
- Opção separada da quantidade tickets abertos e pedentes que carrega tela atendimento
- Permiti abrir ticket em conexão diferente para mesmo contato
- Suporte "instagram v2" do Hub notificame
- Opção Ignorar contato
- Maximo de usuarios e conexões vai respeitar o que esta no plano foi tirado da empresa
- Planos com opção para desativar acesso campanhas, integrações e grupos
- Suporte pagamento Stripe
- Filtro por tags na lista de atendimento
- Tags vem junto com tickets na lista de atendimentos para melhorar desempenho
- Carteiras vem junto com tickets na lista de atendimentos para melhorar desempenho
- Filtro para admin por usuario ou canal
- Hub caso não tenha nome "Name Unavailable" tenta atualizar nas próximas mensagens
- Arquivos Public separado por empresa
- Cache arquivos TypeBot - Sistema vai baixar arquivos e deixar salvo servidor não ter baixar cada vez que fluxo inicia melhorando velocidade e diminuindo consumo recursos
- Videos youtube colocados no Typebot seram baixados e colocados no cache