# 📘 Capítulo 1 – Começando com Git

---

## 1.1 O que é Git

Git é um sistema de controle de versão distribuído, gratuito e de código aberto. Ele é usado para registrar o histórico de mudanças em projetos, especialmente de software. Diferente de ferramentas como Subversion (SVN), o Git armazena dados como uma série de **instantâneos (snapshots)**, e não como diferenças entre versões.

---

## 1.2 Um Pouco de História

O Git foi criado em 2005 por **Linus Torvalds**, criador do kernel Linux. Ele surgiu após o rompimento da comunidade Linux com o sistema proprietário BitKeeper. Linus definiu que o novo sistema deveria ser:

- Rápido
- Simples
- Seguro
- Distribuído
- Capaz de lidar com grandes projetos

---

## 1.3 Estrutura Conceitual do Git

O Git opera em três áreas principais:

| Área                    | Função                                                                 |
|-------------------------|------------------------------------------------------------------------|
| **Diretório de trabalho** | Onde os arquivos são editados                                          |
| **Staging area (index)** | Onde as alterações são preparadas para o commit                        |
| **Repositório (repository)** | Onde os commits são armazenados de forma permanente               |

Fluxo básico:
```bash
# Modifique arquivos
git add arquivo.txt        # envia para o stage
git commit -m "Mensagem"   # salva no histórico
```

---

## 1.4 Instalando o Git

Windows:
Acesse: https://git-scm.com

Baixe o instalador do Git para Windows

Durante a instalação, selecione a opção Git Bash e mantenha as configurações padrão

Linux:
```bash
sudo apt install git       # Debian/Ubuntu
sudo dnf install git       # Fedora
```

macOS:
```bash
brew install git
```

---

## 1.5 Configurando o Git

Após instalar, defina seu nome e e-mail (obrigatórios para qualquer commit):
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```

Configure o editor de texto (opcional):
```bash
git config --global core.editor "code --wait"
```

Verifique suas configurações com:
```bash
git config --list
```

---

## 1.6 Usando Alias

Com alias, você pode abreviar comandos comuns:
```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.cm "commit -m"
```

Agora é possível usar:
```bash
git st
git co main
git cm "Mensagem"
```

---

## 1.7 Escopos de Configuração

| Escopo     | Comando                  | Aplicação                                 |
|------------|--------------------------|-------------------------------------------|
| Local      | `git config`             | Repositório atual (`.git/config`)         |
| Global     | `git config --global`    | Todos os repositórios do usuário          |
| System     | `git config --system`    | Todos os usuários da máquina              |

---

## 1.8 Obtendo Ajuda

O Git possui ajuda embutida:
```bash
git help <comando>
git <comando> --help
```

Exemplo:
```bash
git help commit
```

Acesse também: https://git-scm.com/docs

---

## 1.9 Resumo

- Git armazena dados como snapshots
- Trabalha com área de trabalho, staging e repositório
- git config define identidade e preferências
- git help fornece ajuda detalhada
- Instalação e uso são multiplataforma

---
