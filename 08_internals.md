# 📘 Capítulo 8 – Por Dentro do Git (Internals)

---

## 8.1 Visão Geral

O Git funciona como um banco de dados de objetos. Ele armazena arquivos, diretórios, commits e metadados em estruturas organizadas e identificadas por hashes SHA-1.

Todos os dados do repositório ficam na pasta `.git/`.

---

## 8.2 Estrutura do Diretório `.git/`

| Arquivo/Pasta     | Descrição                                             |
|-------------------|--------------------------------------------------------|
| `HEAD`            | Aponta para a branch atual                            |
| `config`          | Configurações locais do repositório                   |
| `index`           | Área de preparação (staging)                          |
| `objects/`        | Objetos do Git (blobs, trees, commits, tags)          |
| `refs/`           | Referências para branches e tags                      |
| `logs/`           | Histórico de atualizações de refs e HEAD              |

---

## 8.3 Tipos de Objetos do Git

O Git armazena tudo como objetos identificados por SHA-1.

| Tipo     | Função                                                            |
|----------|-------------------------------------------------------------------|
| `blob`   | Conteúdo de um arquivo                                            |
| `tree`   | Representa um diretório, contendo blobs e outras trees           |
| `commit` | Contém metadados e aponta para uma `tree`                        |
| `tag`    | Marca um commit com uma descrição legível                        |

---

## 8.4 Criando Objetos Manualmente

Crie um repositório e adicione um arquivo:

```bash
git init
echo "Olá Git" > exemplo.txt
git add exemplo.txt
```

Antes do commit, o Git já criou um blob para o conteúdo.

Visualize o hash SHA-1:

```bash
git hash-object exemplo.txt
```

---

## 8.5 Explorando Objetos

Visualize o conteúdo de um objeto com:

```bash
git cat-file -p <hash>
```

Descubra o tipo do objeto:

```bash
git cat-file -t <hash>
```

---

## 8.6 Como um Commit é Formado

Ao fazer um commit:

1. O Git cria um objeto ```tree``` com a estrutura do diretório
2. Cria um objeto ```commit``` apontando para a ```tree```
3. Atualiza ```HEAD``` para apontar para esse commit

---

## 8.7 Referências e HEAD

- ```HEAD``` aponta para a branch ativa
- ```refs/heads/``` contém os ponteiros das branches locais
- ```refs/tags/``` contém as tags criadas

---

## 8.8 Reflog: Histórico Oculto

O ```reflog``` registra todas as movimentações de ```HEAD```:

```bash
git reflog
```

Você pode recuperar commits mesmo após ```reset``` ou ```checkout``` equivocados.

---

## 8.9 Compactação com ```git gc```

O Git armazena objetos inicialmente de forma solta. Com o tempo, ele compacta os dados com:

```bash
git gc
```

Isso otimiza espaço e desempenho.

---

## 8.10 Criando Commits com Comandos Baixo Nível

Você pode criar commits manualmente (raramente necessário):

```bash
git write-tree
git commit-tree <hash-da-tree> -m "Mensagem"
```

Isso é como o Git cria commits internamente.

---

## 8.11 Resumo

- O Git armazena tudo como objetos (blob, tree, commit, tag)
- Cada objeto é identificado por um hash SHA-1
- A pasta ```.git/``` contém toda a base de dados
- ```HEAD```, ```refs/```, ```index``` e ```objects/``` são centrais para o funcionamento
- ```git reflog``` recupera movimentos de HEAD
- ```git gc``` compacta e otimiza o repositório

---
