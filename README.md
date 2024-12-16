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