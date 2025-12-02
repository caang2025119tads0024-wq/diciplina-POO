# Guia Prático: Git e GitHub

## O que é Git?
Git é um sistema de controle de versão que permite rastrear mudanças em seus arquivos, criar histórico de alterações e colaborar com outras pessoas.

## O que é GitHub?
GitHub é uma plataforma online que hospeda repositórios Git, permitindo compartilhar código, colaborar em projetos e gerenciar versões de forma centralizada.

---

## 1. Instalação

### Baixar e Instalar Git
- Acesse: https://git-scm.com/download/win
- Execute o instalador e siga as instruções padrão
- Abra o Git Bash ou terminal e verifique: `git --version`

### Criar Conta GitHub
- Acesse: https://github.com
- Clique em "Sign up" e siga o processo de registro

---

## 2. Configuração Inicial do Git

Após instalar, configure seu nome e email:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@example.com"
```

Verifique a configuração:
```bash
git config --list
```

---

## 3. Criar um Repositório Localmente

### Opção A: Criar pasta local e inicializar Git

```bash
# Criar pasta do projeto
mkdir meu_projeto
cd meu_projeto

# Inicializar repositório Git
git init

# Criar arquivo inicial (opcional)
echo "# Meu Projeto" > README.md

# Adicionar arquivo ao Git
git add README.md

# Fazer commit (guardar mudança)
git commit -m "Commit inicial"
```

### Opção B: Clonar um repositório existente do GitHub

```bash
git clone https://github.com/usuario/nome-repositorio.git
cd nome-repositorio
```

---

## 4. Comandos Básicos do Git

### Ver status dos arquivos
```bash
git status
```

### Adicionar arquivos (stage)
```bash
# Adicionar arquivo específico
git add nome_arquivo.txt

# Adicionar todos os arquivos
git add .
```

### Fazer commit (guardar mudança com mensagem)
```bash
git commit -m "Descrição da mudança"
```

### Ver histórico de commits
```bash
git log
git log --oneline  # Versão resumida
```

### Ver mudanças não confirmadas
```bash
git diff
```

---

## 5. Trabalhar com GitHub

### Criar um repositório no GitHub

1. Entre em https://github.com
2. Clique no ícone **+** (canto superior direito)
3. Selecione **New repository**
4. Preencha o nome, descrição (opcional) e clique **Create repository**

### Conectar repositório local ao GitHub

```bash
# Adicionar repositório remoto
git remote add origin https://github.com/seu_usuario/seu_repositorio.git

# Renomear branch (se necessário - Git usa 'main' por padrão)
git branch -M main

# Enviar código para GitHub (push)
git push -u origin main
```

### Enviar mudanças para GitHub

```bash
# 1. Adicionar mudanças
git add .

# 2. Fazer commit
git commit -m "Descrição das mudanças"

# 3. Enviar para GitHub
git push
```

### Trazer mudanças do GitHub

```bash
# Baixar atualizações (sem mesclar)
git fetch

# Baixar e mesclar atualizações
git pull
```

---

## 6. Branches (Ramos)

Branches permitem trabalhar em funcionalidades sem afetar o código principal.

```bash
# Ver branches
git branch

# Criar novo branch
git branch nome_novo_branch

# Mudar para um branch
git checkout nome_branch
git switch nome_branch  # Sintaxe mais recente

# Criar e mudar para novo branch em um comando
git checkout -b nome_novo_branch

# Deletar branch
git branch -d nome_branch

# Mesclar branch (merge)
git merge nome_branch
```

---

## 7. Fluxo Típico de Trabalho

```bash
# 1. Criar/clonar repositório
git clone https://github.com/usuario/projeto.git
cd projeto

# 2. Criar novo branch para sua funcionalidade
git checkout -b nova-funcionalidade

# 3. Fazer mudanças nos arquivos
# ... edite os arquivos ...

# 4. Adicionar mudanças
git add .

# 5. Fazer commit
git commit -m "Adiciona nova funcionalidade"

# 6. Enviar para GitHub
git push -u origin nova-funcionalidade

# 7. No GitHub, abrir Pull Request (PR)
# 8. Revisar e mesclar na branch main
```

---

## 8. Comandos Úteis

```bash
# Desfazer último commit (mantendo mudanças)
git reset --soft HEAD~1

# Desfazer mudanças em arquivo específico
git checkout -- nome_arquivo.txt

# Renomear último commit
git commit --amend -m "Nova mensagem"

# Limpar arquivos não rastreados
git clean -fd

# Ver quem modificou cada linha
git blame nome_arquivo.txt
```

---

## 9. .gitignore

Arquivo que especifica quais arquivos Git deve ignorar.

Criar `.gitignore` na raiz do projeto:

```
# Extensões
*.exe
*.obj
*.o
*.a
*.so

# Pastas
node_modules/
.vscode/
__pycache__/
.vs/

# Arquivos específicos
.env
config.local.json
database.db
```

---

## 10. Troubleshooting Comum

### Erro: "fatal: not a git repository"
Solução: Execute `git init` na pasta do projeto

### Erro ao fazer push: "rejected"
Solução: Faça `git pull` antes de `git push` para sincronizar mudanças

### Esqueceu a senha do GitHub
Solução: Configure chave SSH (mais seguro que senha)
```bash
ssh-keygen -t ed25519 -C "seu.email@example.com"
```

### Ver configuração remota
```bash
git remote -v
```

---

## Dicas Práticas

✅ Faça commits pequenos e frequentes  
✅ Use mensagens de commit descritivas  
✅ Sincronize com `git pull` regularmente  
✅ Use branches para novas funcionalidades  
✅ Revise mudanças antes de fazer push  
✅ Sempre trabalhe em uma branch, não na main  

---

## Recursos Adicionais

- **Git Documentation**: https://git-scm.com/doc
- **GitHub Help**: https://docs.github.com
- **Interactive Git Learning**: https://learngitbranching.js.org
- **GitHub CLI**: https://cli.github.com (controlar GitHub pelo terminal)
