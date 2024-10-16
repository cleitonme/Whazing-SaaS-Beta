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

Versão: 2.6.0 BETA

- Suporte facebook e instagram  e WebChat via hub (função exclusiva versão premium)
- Melhorias de segurança socket
- Respeitar delay Typebot
- Deletar um canal definitivamente agora, antes somente ocultava conexão