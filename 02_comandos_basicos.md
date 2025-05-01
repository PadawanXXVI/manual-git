# 📘 Capítulo 2 – Comandos Básicos do Git

---

## 2.1 Criando um Repositório

Você pode iniciar o controle de versão em um diretório já existente com:

```bash
git init
```

Isso cria um repositório Git local na pasta ```.git/.```

---

## 2.2 Clonando um Repositório

Para obter uma cópia de um projeto existente:
```bash
git clone https://github.com/usuario/repositorio.git
```

O Git criará uma cópia completa do histórico e conectará automaticamente ao repositório remoto como ```origin```.

---

## 2.3 Verificando o Status

Para ver quais arquivos foram modificados, adicionados ou removidos:
```bash
git status
```

Esse comando mostra o que está pendente para adicionar ou commit.

---

## 2.4 Adicionando Arquivos ao Staging

Antes de confirmar (fazer commit), adicione as alterações à área de preparação:
```bash
git add arquivo.txt
```

Para adicionar tudo:
```bash
git add .
```

---

## 2.5 Fazendo Commits

Grave um snapshot do seu projeto com uma mensagem descritiva:
```bash
git commit -m "Mensagem clara sobre o que foi feito"
```

---

## 2.6 Visualizando o Histórico
```bash
git log
```

Exibe todos os commits da branch atual, em ordem cronológica reversa.

Versões úteis:
```bash
git log --oneline --graph --all
```

---

## 2.7 Revertendo Alterações

Para descartar modificações **não adicionadas ao stage**:
```bash
git restore arquivo.txt
```

Para remover um arquivo do stage:
```bash
git restore --staged arquivo.txt
```

---

## 2.8 Ignorando Arquivos

Crie um arquivo ```.gitignore``` na raiz do repositório:

Exemplo:
```bash
*.log
*.tmp
node_modules/
.env
```

---

## 2.9 Removendo Arquivos

Para remover um arquivo do projeto e da área de staging:
```bash
git rm arquivo.txt
git commit -m "Remove arquivo.txt"
```

---

## 2.10 Renomeando ou Movendo Arquivos
```bash
git mv antigo.txt novo.txt
git commit -m "Renomeia antigo.txt para novo.txt"
```

---

## 2.11 Resumo

- ```git init```: cria um novo repositório
- ```git clone```: copia um repositório remoto
- ```git status```: mostra o estado atual dos arquivos
- ```git add```: prepara arquivos para commit
- ```git commit```: grava as mudanças
- ```git log```: exibe histórico
- ```git restore```: desfaz mudanças
- ```git rm```, ```git mv```: removem ou renomeiam arquivos
- ```.gitignore```: exclui arquivos do controle de versão

---
