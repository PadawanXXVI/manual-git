# 📘 Capítulo 7 – Git e Outros Sistemas

---

## 7.1 Trabalhando com Subversion (SVN)

O Git possui suporte nativo a repositórios **Subversion** por meio do comando `git svn`.

### Clonando um repositório SVN:

```bash
git svn clone https://servidor.com/repositorio caminho-local
```

Esse processo pode demorar, pois o Git converte o histórico inteiro do SVN.

---

## 7.2 Sincronizando com SVN

Buscar atualizações do repositório SVN:

```bash
git svn fetch
```

Enviar commits locais de volta ao servidor SVN:

```bash
git svn dcommit
```

---

## 7.3 Comparação Git vs SVN

| Conceito        | SVN                      | Git                             |
|-----------------|--------------------------|----------------------------------|
| Centralização   | Sim                      | Não (distribuído)                |
| Branches        | Pesadas, cópia do diretório | Leves, ponteiros internos     |
| Histórico local | Não                      | Sim                              |
| Velocidade      | Menor                    | Alta                             |

---

## 7.4 Importando de CVS

O Git não suporta CVS nativamente, mas você pode usar ferramentas como:

Usando ```git cvsimport```:

```bash
git cvsimport -v -d /caminho/para/cvsrepos -C projeto-novo nome-do-módulo
```

Alternativa: ```cvs2git``` (ferramenta externa)

- Converte repositórios CVS para Git com mais precisão
- Requer Python e dependências específicas

---

## 7.5 Migrando de Outros Sistemas

Você pode migrar projetos de:

- Mercurial (Hg)
- TFS
- Perforce
- ClearCase

Ferramentas como ```hg-fast-export```, ```git-tfs```, ou exportação de patches ```.diff``` ajudam nesse processo.

---

## 7.6 Aplicando Patches de Sistemas Externos

Se outro sistema gerar arquivos .patch ou .diff, você pode aplicar com:

```bash
git apply arquivo.patch
```

Ou criar commits com:

```bash
git am arquivo.patch
```

---

## 7.7 Iniciando o Controle de Versão em Projetos Legados

Se o projeto não possui controle de versão, inicie com:

```bash
cd projeto/
git init
git add .
git commit -m "Importação do projeto"
```

---

## 7.8 Resumo

- Git pode interagir com SVN através do git svn
- CVS pode ser migrado com ferramentas como cvs2git ou git cvsimport
- Outros sistemas como Mercurial, TFS e Perforce exigem ferramentas específicas
- Você pode iniciar o controle de versão em qualquer projeto legando com git init

---
