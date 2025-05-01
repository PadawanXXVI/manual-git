# 📘 Capítulo 6 – Personalizando o Git

---

## 6.1 Configurações Avançadas com `git config`

Além das configurações básicas de nome e e-mail, você pode ajustar o comportamento do Git com `git config`.

### Exemplo: definir ferramenta de merge
```bash
git config --global merge.tool vimdiff
```

Desativar conversão automática de final de linha

```bash
git config --global core.autocrlf false
```

Definir o editor padrão

```bash
git config --global core.editor "code --wait"
```

---

## 6.2 Hooks: Automatizando o Fluxo

Git hooks são scripts executados automaticamente em determinados eventos, como antes de um commit ou após um merge.

Localização:

```bash
.git/hooks/
```

Exemplo: impedir commits sem mensagem

Edite ```.git/hooks/commit-msg```:

```bash
#!/bin/sh
test -z "$(cat "$1")" && {
  echo "A mensagem de commit não pode estar vazia."
  exit 1
}
```

Torne o script executável:

```bash
chmod +x .git/hooks/commit-msg
```

⚠️ Hooks não são versionados com o repositório. Para compartilhamento, use ferramentas como Husky.

---

## 6.3 Alias Personalizados

Alias simplificam comandos frequentes:

```bash
git config --global alias.s status
git config --global alias.cm "commit -m"
git config --global alias.hist "log --oneline --graph --decorate --all"
```

Uso:

```bash
git s
git cm "mensagem"
git hist
```

---

## 6.4 Condições por Diretório (Configuração Condicional)

Você pode aplicar configurações específicas para certos diretórios de projeto:

```bash
[includeIf "gitdir:~/projetos/empresa/"]
  path = ~/.gitconfig-empresa
```

---

## 6.5 Subcomandos Personalizados

Se você criar um script chamado ```git-relatorio```, poderá executá-lo como:

```bash
git relatorio
```

O script deve estar em um diretório incluído no ```PATH``` do sistema.

---

## 6.6 Integração com Ferramentas Externas

Você pode definir ferramentas específicas para edição, comparação ou merge.

Exemplo com Visual Studio Code:


```bash
git config --global core.editor "code --wait"
git config --global merge.tool vscode
```

---

## 6.7 Resumo

- git config permite configurar quase tudo no Git
- Hooks automatizam ações como verificação antes de commit
- Alias otimizam produtividade com comandos abreviados
- Configurações condicionais adaptam o ambiente conforme o projeto
- Ferramentas externas (como VS Code) podem ser integradas

---
