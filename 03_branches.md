# 📘 Capítulo 3 – Ramificações no Git (Branches)

---

## 3.1 O que é uma Branch?

Uma **branch** (ramificação) representa uma linha independente de desenvolvimento. Ela permite que você trabalhe em funcionalidades, correções ou testes sem afetar a versão principal do projeto.

O Git torna a criação e o gerenciamento de branches extremamente leve e eficiente, incentivando o uso constante de ramificações.

---

## 3.2 Criando uma Nova Branch

```bash
git branch minha-branch
```

Isso cria uma nova branch baseada na branch atual, mas não muda para ela.

---

## 3.3 Alternando Entre Branches

```bash
git checkout minha-branch
```

Ou, com o Git 2.23+:

```bash
git switch minha-branch
```

---

## 3.4 Criar e Mudar em Um Único Comando

```bash
git checkout -b nova-feature
```

Ou:

```bash
git switch -c nova-feature
```

---

## 3.5 Listando Branches

```bash
git branch
```

A branch atual estará marcada com um asterisco ```*```.

Para ver branches remotas:

```bash
git branch -a
```

---

## 3.6 Unindo Branches com ```merge```

Mude para a branch de destino (ex: main) e execute:

```bash
git merge nova-feature
```

Se não houver conflitos, o Git aplicará automaticamente as mudanças.

---

## 3.7 Excluindo Branches

Após o merge ou se uma branch não for mais necessária:

```bash
git branch -d nome-da-branch
```

Para forçar a exclusão:

```bash
git branch -D nome-da-branch
```

---

## 3.8 Conflitos de Merge

Quando dois commits alteram a mesma parte de um arquivo, o Git sinaliza um **conflito**, que deve ser resolvido manualmente:

```plaintext
<<<<<<< HEAD
código da branch atual
=======
código da branch mesclada
>>>>>>> nome-da-branch
```

Após resolver, marque como resolvido:

```bash
git add arquivo.txt
git commit
```

---

## 3.9 Estratégias de Merge

- Fast-forward: aplica os commits diretamente se não houver divergência
- Merge commit: cria um commit de junção (padrão)
- Rebase: reescreve o histórico aplicando commits em nova base (ver Capítulo 6)

---

## 3.10 Fluxo de Trabalho com Branches

Um fluxo comum é:

```plaintext
main
│
├── nova-feature → commits isolados
│
└── merge na main
```

Isso permite revisão, testes e isolamento antes da integração.

---

## 3.11 Resumo

- ```git branch```: cria, lista ou exclui branches
- ```git checkout``` / ```git switch```: muda de branch
- ```git merge```: integra mudanças
- Conflitos devem ser resolvidos manualmente
- O uso de branches facilita organização e colaboração

---
