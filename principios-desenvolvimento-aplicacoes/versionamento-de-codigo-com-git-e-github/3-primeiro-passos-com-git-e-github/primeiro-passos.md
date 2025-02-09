# Aula 3 - Primeiros Passos com Git e GitHub

Nesta aula, vamos aprender como **criar e clonar repositórios**, **salvar alterações**, **desfazer mudanças**, **enviar e baixar alterações de repositórios remotos** e trabalhar com **branches** no Git. Além disso, abordaremos alguns **comandos úteis no dia a dia** para facilitar o trabalho com Git e GitHub.

---

## 1. Criando e Clonando Repositórios

### **Criando um Repositório no GitHub**

1. Acesse o [GitHub](https://github.com/) e faça login na sua conta.
2. No canto superior direito, clique no ícone de **+** e selecione **"New repository"**.
3. Preencha o nome do repositório, descrição e escolha se ele será público ou privado.
4. Após preencher, clique em **"Create repository"**.

Agora, seu repositório foi criado no GitHub, mas ainda não contém arquivos. Para adicionar arquivos, você precisará cloná-lo para seu computador local.

### **Clonando um Repositório**

Para clonar um repositório já existente (seja o seu ou de outra pessoa), use o comando `git clone`:

```bash
git clone <url-do-repositorio>
```

Substitua `<url-do-repositorio>` pela URL do repositório que você deseja clonar. O Git cria uma cópia local do repositório no seu computador, permitindo que você trabalhe no código.

---

## 2. Salvando Alterações no Repositório Local

Depois de fazer alterações em seus arquivos, você precisa **salvar essas mudanças** no Git. Para isso, o Git utiliza os **commits**.

### **Comandos para Salvar Alterações**:

1. **Adicionar arquivos ao índice** (staging area):

   Para começar a controlar os arquivos alterados, use o comando `git add`:

   ```bash
   git add <nome-do-arquivo>
   ```

   Para adicionar todos os arquivos alterados de uma vez:

   ```bash
   git add .
   ```

2. **Fazer o commit das alterações**:

   Após adicionar os arquivos, você precisa fazer um **commit** para salvar as alterações de maneira permanente:

   ```bash
   git commit -m "Mensagem do commit explicando as alterações"
   ```

3. **Verificar o status do repositório**:

   Para ver quais arquivos foram modificados, adicionados ou estão pendentes de commit, use:

   ```bash
   git status
   ```

---

## 3. Desfazendo Alterações no Repositório Local

Às vezes, você pode querer **desfazer alterações** que fez no repositório local. Aqui estão algumas formas de fazer isso:

### **Desfazendo Modificações em Arquivos Não Commitados**:

Se você ainda não fez o commit e quer desfazer mudanças em um arquivo, use:

```bash
git checkout -- <nome-do-arquivo>
```

### **Desfazendo Commits Locais**:

Se você já fez o commit, mas quer desfazê-lo, use:

- **Para desfazer o commit, mas manter as alterações no seu diretório de trabalho**:

   ```bash
   git reset --soft HEAD^
   ```

- **Para desfazer o commit e as alterações do diretório de trabalho**:

   ```bash
   git reset --hard HEAD^
   ```

---

## 4. Enviando e Baixando Alterações com o Repositório Remoto

Agora que você já sabe salvar alterações localmente, vamos ver como **enviar** e **baixar** alterações de um repositório remoto (no GitHub, por exemplo).

### **Enviando Alterações para o Repositório Remoto (git push)**:

Depois de salvar as alterações no repositório local, use o comando `git push` para enviá-las para o repositório remoto:

```bash
git push origin <nome-da-branch>
```

Substitua `<nome-da-branch>` pela branch onde você deseja enviar as alterações (geralmente `main` ou `master`).

### **Baixando Alterações do Repositório Remoto (git pull)**:

Se outra pessoa fez alterações no repositório remoto e você quer obter essas mudanças, use o comando `git pull`:

```bash
git pull origin <nome-da-branch>
```

Isso baixa e mescla as alterações do repositório remoto na sua cópia local.

---

## 5. Trabalhando com Branches

As **branches** (ramificações) são um dos conceitos mais poderosos do Git. Elas permitem que você trabalhe em diferentes partes de um projeto sem afetar a versão principal do código.

### **Criando uma Nova Branch**:

Para criar uma nova branch, use o comando:

```bash
git checkout -b <nome-da-branch>
```

Isso cria e muda para a nova branch.

### **Mudando para uma Branch Existente**:

Se você já tem uma branch existente e deseja mudar para ela, use:

```bash
git checkout <nome-da-branch>
```

### **Mesclando Branches** (Merging):

Depois de fazer alterações em uma branch, você pode querer **mesclar** essas alterações na branch principal. Para fazer isso, primeiro mude para a branch onde você deseja aplicar as alterações (geralmente `main` ou `master`) e depois use o comando `git merge`:

```bash
git checkout main
git merge <nome-da-branch>
```

Isso mescla as alterações da `<nome-da-branch>` na branch atual.

### **Deletando uma Branch**:

Depois de terminar de trabalhar em uma branch e mesclá-la com a branch principal, você pode querer **deletá-la**. Use o comando:

```bash
git branch -d <nome-da-branch>
```

Se você não tiver feito o merge da branch e quiser forçar a exclusão, use:

```bash
git branch -D <nome-da-branch>
```

---

## 6. Tratando Conflitos de Merge

Às vezes, quando você tenta mesclar duas branches, pode ocorrer um **conflito de merge**. Isso acontece quando o Git não consegue decidir automaticamente como combinar as alterações. Para resolver o conflito:

1. O Git marcará os arquivos com conflitos.
2. Abra os arquivos conflitantes e resolva os conflitos manualmente. O Git marcará as seções conflitantes, permitindo que você escolha qual alteração manter.
3. Após resolver os conflitos, marque os arquivos como resolvidos com:

   ```bash
   git add <nome-do-arquivo>
   ```

4. Complete o merge com:

   ```bash
   git commit
   ```

---

## 7. Comandos Úteis no Dia a Dia

Aqui estão alguns **comandos úteis no dia a dia** para facilitar o trabalho com Git:

- **Ver o histórico de commits**:

   ```bash
   git log
   ```

- **Mostrar as diferenças entre o repositório local e o remoto**:

   ```bash
   git diff
   ```

- **Ver os arquivos modificados**:

   ```bash
   git diff --name-only
   ```

- **Ver a diferença entre commits**:

   ```bash
   git diff <commit-id> <commit-id>
   ```

---

## Conclusão

Nesta aula, abordamos os primeiros passos com Git e GitHub, desde a **criação e clonagem de repositórios** até **trabalhar com branches** e **resolver conflitos de merge**. Esses são conceitos fundamentais para o gerenciamento de versões e colaboração em projetos de software.

Agora você está pronto para começar a usar o Git no seu dia a dia de desenvolvimento!

Se precisar de mais detalhes ou ajuda, consulte a [documentação oficial do Git](https://git-scm.com/doc) ou o [GitHub Docs](https://docs.github.com/en/github).