Como atualizar


coloca na pasta /home/deploy/whazing
No terminal
su deploy
cd /home/deploy/whazing
unzip -o whazing.zip
chmod 775 /home/deploy/whazing/ -Rf
cd backend
npm install --force
npx sequelize db:migrate
pm2 restart all

cd ..
cd frontend
npm install --force
npm run build

Importante: Sempre usar usuario deploy nao esquece

Versão: 2.5.0 BETA

- bug - revisado opção deletar empresa para evitar erros
- bug - retornar ticket para fila limpa usuario
- bug - painel atendimento não mostra mais tickets fechados
- Pagina usuarios foi colocado exibir id para ser mais facil usar no TypeBot
- Integração  ChatGPT
- Integração Groq
- Integração Microsoft Azure Text-to-Speech
- Opção mensagem despedida personalizadas, pelo admin e pelos usuarios, admin pode criar, vizualizar e editar mensagens de todos usuarios,Usuarios somente podem acessar suas proprias mensagens 
- Mudança sistemas de variaveis e novas variaveis consultar arquivo pasta docs
- Opção escolher ocultar tabs ou não tela de atendimento
- ChatFlow opção enviar mensagem ao roteador para fila ou usuario
- Opção cadastro usuario para ignorar carteira mostrar todos contatos