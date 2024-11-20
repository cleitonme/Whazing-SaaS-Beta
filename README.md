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

Versão 2.7.4 beta

############### INTEGRAÇÕES SOMENTE PARA VERSÃO PREMIUM ###################

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