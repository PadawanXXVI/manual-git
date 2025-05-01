# 📘 Capítulo 5 – Ferramentas do Git (Git Tools)

---

## 5.1 Marcando Commits com Tags

**Tags** são usadas para marcar versões específicas no histórico do repositório, como lançamentos (`v1.0`, `v2.0.1` etc).

### Criar uma tag leve:
```bash
git tag v1.0
```

Criar uma tag anotada (com metadados):

```bash
git tag -a v1.0 -m "Versão 1.0 lançada"
```

Listar tags:

```bash
git tag
```

Ver detalhes de uma tag:

```bash
git show v1.0
```

Enviar tags ao remoto:

```bash
git push origin v1.0          # envia uma
git push origin --tags        # envia todas
```

---

## 5.2 Armazenando Mudanças Temporárias com stash

Use stash para guardar alterações temporariamente sem fazer commit:

```bash
git stash
```

Ver lista de stashes:

```bash
git stash list
```

Reaplicar:

```bash
git stash apply
```

Reaplicar e remover:

```bash
git stash pop
```

---

## 5.3 Encontrando Bugs com ```bisect```

O comando git bisect ajuda a localizar em qual commit um bug foi introduzido, utilizando busca binária.

Exemplo:

```bash
git bisect start
git bisect bad                # commit com bug
git bisect good <hash-bom>   # commit funcional
```

Teste os commits intermediários e o Git indicará o commit problemático. Finalize com:

```bash
git bisect reset
```

---

## 5.4 Visualizando Alterações com ```git diff```

Diferença entre diretório de trabalho e staging:

```bash
git diff
```

Diferença entre staging e último commit:

```bash
git diff --cached
```

Diferença entre dois commits:

```bash
git diff commit1 commit2
```

---

## 5.5 Analisando o Histórico

```git log``` com detalhes:

```bash
git log -p
```

Visual com gráfico:

```bash
git log --oneline --graph --decorate --all
```

Histórico por autor:

```bash
git shortlog -sn
```

---

## 5.6 Usando git blame

Mostra quem modificou cada linha de um arquivo:

```bash
git blame arquivo.txt
```

Muito útil para auditoria e revisão de histórico.

--- 

## 5.7 Criando Aliases

Torne comandos longos mais curtos com aliases:

```bash
git config --global alias.hist "log --oneline --graph --decorate --all"
git config --global alias.st status
git config --global alias.cm "commit -m"
```

Agora você pode usar:

```bash
git hist
git st
git cm "mensagem"
```

---

## 5.8 Resumo

Ferramentas úteis no dia a dia com Git:

- ```git tag```: marca versões
- ```git stash```: armazena mudanças temporárias
- ```git bisect```: ajuda a encontrar o commit com bug
- ```git diff```, ```log```, ```blame```: analisam alterações
- ```git alias```: personaliza comandos

---
