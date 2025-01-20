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

Não tem versão disponivel

