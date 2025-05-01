# 📘 Capítulo 4 – Trabalhando com Repositórios Remotos

---

## 4.1 O que são Repositórios Remotos?

Repositórios remotos são versões do seu projeto hospedadas em servidores online, como o **GitHub**, **GitLab** ou **Bitbucket**. Eles permitem colaboração e sincronização entre múltiplos desenvolvedores.

---

## 4.2 Verificando Repositórios Remotos

Para listar os repositórios remotos vinculados ao seu projeto:

```bash
git remote -v
```

A saída típica é:

```bash
origin  https://github.com/usuario/repositorio.git (fetch)
origin  https://github.com/usuario/repositorio.git (push)
```

---

## 4.3 Adicionando um Repositório Remoto

Se você criou o projeto localmente, adicione o repositório remoto com:

```bash
git remote add origin https://github.com/usuario/repositorio.git
```

---

## 4.4 Enviando Commits para o Servidor (Push)

Após fazer commits localmente, envie as alterações para o repositório remoto:

```bash
git push origin main
```

Use ```--set-upstream``` se for o primeiro envio:

```bash
git push --set-upstream origin main
```

---

## 4.5 Obtendo Atualizações do Remoto

🔁 git fetch – busca atualizações sem aplicar:

```bash
git fetch origin
```

⬇️ git pull – busca e aplica atualizações:

```bash
git pull origin main
```

```git pull``` = ```git fetch``` + ```git merge```

## 4.6 Trabalhando com Várias Remotas

Você pode ter múltiplos repositórios remotos:

```bash
git remote add upstream https://github.com/outrousuario/repositorio.git
git fetch upstream
git merge upstream/main
```

---

## 4.7 Renomeando ou Removendo um Remoto

Renomear:

```bash
git remote rename origin github
```

Remover:

```bash
git remote remove origin
```

---

## 4.8 Clonando um Repositório Remoto

Para iniciar um projeto localmente a partir de um repositório remoto:

```bash
git clone https://github.com/usuario/repositorio.git
```

Isso cria um diretório com o projeto e já vinculado ao remoto ```origin```.

---

## 4.9 Autenticação e Acesso

HTTPS:
- Exige autenticação por token de acesso pessoal (em vez de senha).

SSH:
1. Gere uma chave com ssh-keygen
2. Adicione a chave pública ao GitHub
3. Use o endereço SSH:

```bash
git remote set-url origin git@github.com:usuario/repositorio.git
```

---

## 4.10 Resumo

- git remote gerencia conexões com repositórios remotos
- git push envia commits
- git fetch e git pull trazem atualizações
- git clone cria um repositório local a partir de um remoto
- A autenticação pode ser feita via HTTPS (com token) ou SSH

---
