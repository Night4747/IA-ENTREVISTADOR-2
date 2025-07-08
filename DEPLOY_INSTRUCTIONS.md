# 🚀 Instruções para Deploy no Heroku

## 📋 Pré-requisitos

### 1. Criar Conta Gratuita no Heroku
1. Acesse: https://signup.heroku.com/
2. Preencha os dados:
   - **First Name**: Seu primeiro nome
   - **Last Name**: Seu sobrenome
   - **Email**: Seu email válido
   - **Company**: Opcional (pode deixar em branco)
   - **Role**: Selecione "Student" ou "Hobbyist"
   - **Country**: Brasil
   - **Development Language**: Python
3. Clique em "CREATE FREE ACCOUNT"
4. Verifique seu email e confirme a conta
5. Defina uma senha quando solicitado

### 2. Instalar Heroku CLI (se necessário)
Se você não tem o Heroku CLI instalado em seu computador:

**Windows:**
- Baixe de: https://devcenter.heroku.com/articles/heroku-cli
- Execute o instalador

**macOS:**
```bash
brew tap heroku/brew && brew install heroku
```

**Linux:**
```bash
curl https://cli-assets.heroku.com/install.sh | sh
```

## 🔧 Arquivos Preparados para Deploy

Todos os arquivos necessários já estão configurados:

- ✅ **Procfile**: Define como o Heroku deve executar a aplicação
- ✅ **requirements.txt**: Lista todas as dependências Python
- ✅ **runtime.txt**: Especifica a versão do Python
- ✅ **.gitignore**: Ignora arquivos desnecessários
- ✅ **run_server.py**: Script principal configurado para Heroku

## 🚀 Comandos para Deploy

### 1. Fazer Login no Heroku
```bash
heroku login
```
- Isso abrirá seu navegador para fazer login
- Faça login com as credenciais criadas

### 2. Criar Aplicação no Heroku
```bash
heroku create ia-entrevistador-[SEU-NOME]
```
- Substitua `[SEU-NOME]` por algo único (ex: ia-entrevistador-joao)
- O nome deve ser único globalmente no Heroku

### 3. Fazer Deploy
```bash
git push heroku master
```

### 4. Abrir Aplicação
```bash
heroku open
```

## 📝 Comandos Completos (Copie e Cole)

Abra o terminal na pasta da aplicação e execute:

```bash
# 1. Login no Heroku
heroku login

# 2. Criar app (substitua 'seu-nome' por algo único)
heroku create ia-entrevistador-seu-nome

# 3. Deploy da aplicação
git push heroku master

# 4. Abrir no navegador
heroku open
```

## 🔍 Verificar Status do Deploy

Para verificar se tudo está funcionando:

```bash
# Ver logs da aplicação
heroku logs --tail

# Ver status da aplicação
heroku ps

# Ver informações da aplicação
heroku info
```

## ⚠️ Possíveis Problemas e Soluções

### Problema: Nome da aplicação já existe
**Solução:** Escolha um nome diferente:
```bash
heroku create ia-entrevistador-[OUTRO-NOME]
```

### Problema: Erro de dependências
**Solução:** Verifique se todas as dependências estão no requirements.txt:
```bash
pip freeze > requirements.txt
git add requirements.txt
git commit -m "Update requirements"
git push heroku master
```

### Problema: Aplicação não inicia
**Solução:** Verifique os logs:
```bash
heroku logs --tail
```

### Problema: Erro de porta
**Solução:** O arquivo run_server.py já está configurado para usar a porta do Heroku automaticamente.

## 🎯 URLs Importantes

Após o deploy bem-sucedido, você terá:

- **URL da Aplicação**: https://[NOME-DO-APP].herokuapp.com
- **Dashboard Heroku**: https://dashboard.heroku.com/apps/[NOME-DO-APP]

## 💡 Dicas Importantes

1. **Nome Único**: O nome da aplicação deve ser único no Heroku
2. **Logs**: Use `heroku logs --tail` para debugar problemas
3. **Gratuito**: A conta gratuita tem algumas limitações:
   - App "dorme" após 30 minutos de inatividade
   - 550 horas gratuitas por mês
   - Pode demorar alguns segundos para "acordar"

## 🔄 Atualizações Futuras

Para atualizar a aplicação no futuro:

```bash
# 1. Fazer mudanças no código
# 2. Commit das mudanças
git add .
git commit -m "Descrição das mudanças"

# 3. Deploy da atualização
git push heroku master
```

## 📞 Suporte

Se encontrar problemas:
1. Verifique os logs: `heroku logs --tail`
2. Consulte a documentação: https://devcenter.heroku.com/
3. Verifique se todos os arquivos estão commitados no Git

---

**Boa sorte com o deploy! 🍀**

