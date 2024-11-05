Como atualizar


coloca o arquivo whazing.zip na pasta /home/deploy/whazing
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

Versão 2.7.1 beta

- bug - Configuração alterava de outras empresas com usuario SAAS
- bug - Mensagem vindas de story não chegava
- bug - Cadastro HUB respeitar limite de canais
- bug - conversas 2 empresas diferentes na mesma instalação não confirmava envio da mensagem
- Kanban (somente versão premium)
- Cadastro contato mais facil seleção pais vem brasil padrão não prescisa colocar 55
- Embelezamento numero telefone exibir br no lugar 55 e formatar numero
- Ao tentar abrir ticket caso já exista mostra nome do usuario ou fila para facilitar localização
- ChatFlow interno agora aceita transcrição de audio e reconhece caso cliente envie um arquivo
- Mudança 2 empresas diferentes podem usar mesmo nome de whatsapp
- Proporção videos e imagens tela chat melhorado a vizualização
- Melhoria notificações chat interno
- Configuração para desativar notificações de grupos
- Opção Reabrir tickets anteriores ao receber novas mensagens (Com essa opção ativada caso já exista ticket fechada ele vai abrir ele novamente e não criar um ticket novo.)
- Opção para selecionar tambem nas opção fechar e apagar ticket em Massa
- Opção deletar ticket individual na tela de atendimento( somente aparece admin)
- Baixar conversa - Ticket em PDF
- Colocado botão chamar whatsapp de suporte em pontos estrategicos(Tela inicial, tela solicitar teste, sesão whatsapp, financeiro, integrações e bot)