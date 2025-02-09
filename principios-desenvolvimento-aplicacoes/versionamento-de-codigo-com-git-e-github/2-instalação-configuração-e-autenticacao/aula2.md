# Aula 2 - Instalando, Configurando e Autenticando no Git

Neste guia, abordaremos como **instalar** o Git, **configurá-lo** corretamente e autenticar-se para interagir com repositórios remotos, seja utilizando **token de acesso** ou **chave SSH**.

## 1. Instalando o Git

### **No Windows**

Para instalar o Git no Windows, siga os seguintes passos:

1. Acesse o [site oficial do Git](https://git-scm.com/download/win) para baixar o instalador.
2. O download começará automaticamente. Após o término do download, execute o arquivo de instalação.
3. Durante o processo de instalação, é recomendado deixar as configurações padrão, mas é importante verificar as opções:
   - **Escolher editor de texto**: selecione o editor de sua preferência (como Visual Studio Code ou Notepad++).
   - **Ajuste do PATH**: escolha a opção para adicionar o Git ao PATH do sistema.
   - **Configuração do terminal**: escolha a opção de **"Git Bash"** para usar o terminal próprio do Git.

4. Após a instalação, abra o **Git Bash** (uma interface de linha de comando dedicada ao Git) e digite o seguinte comando para verificar a instalação:

```bash
git --version
```

Isso deve retornar a versão do Git instalada, indicando que o Git foi instalado com sucesso.

---

### **No Ubuntu**

Para instalar o Git no Ubuntu, siga os passos abaixo:

1. Abra o terminal e execute o seguinte comando para garantir que o repositório de pacotes esteja atualizado:

```bash
sudo apt update
```

2. Em seguida, instale o Git com o seguinte comando:

```bash
sudo apt install git
```

3. Após a instalação, verifique a versão instalada para garantir que tudo correu bem:

```bash
git --version
```

---

## 2. Configurando o Git

Após a instalação, é importante configurar seu **nome de usuário** e **email** no Git, para que as alterações feitas no repositório possam ser associadas a você.

Execute os seguintes comandos no terminal para configurar seu nome e email:

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seuemail@exemplo.com"
```

Essas configurações serão usadas em todos os repositórios Git que você criar ou clonar. Caso queira configurar para um repositório específico, basta remover a opção `--global`.

### Verificar a configuração

Para verificar se as configurações foram aplicadas corretamente, use:

```bash
git config --list
```

Isso mostrará todas as configurações atuais do Git.

---

## 3. Autenticando-se no Git

Agora que o Git está instalado e configurado, vamos ver como realizar a **autenticação** para interagir com repositórios remotos. O Git oferece duas maneiras principais de autenticação: **via token** e **via chave SSH**.

---

### **Autenticação via Token de Acesso**

Os tokens de acesso são usados quando você está interagindo com repositórios hospedados no GitHub ou GitLab, por exemplo. Eles substituem a senha tradicional para garantir uma camada extra de segurança.

#### Como criar um token no GitHub:

1. Acesse [GitHub](https://github.com/) e faça login.
2. Vá para **Settings** (Configurações) clicando na sua foto de perfil no canto superior direito.
3. No menu lateral, clique em **Developer settings**.
4. Escolha **Personal access tokens** e depois clique em **Generate new token**.
5. Selecione as permissões desejadas para o token (geralmente, você precisará de permissões de **repo** para acessar repositórios).
6. Clique em **Generate token** e copie o token gerado.

#### Como usar o token:

Quando você for realizar operações como **git push** ou **git pull**, o Git pedirá o seu **usuário** e **senha**. No campo de senha, cole o token de acesso gerado.

---

### **Autenticação via Chave SSH**

A autenticação via chave SSH é uma forma segura de interagir com repositórios sem precisar inserir o token ou senha sempre.

#### Como gerar e adicionar uma chave SSH no GitHub:

1. **Gerar uma chave SSH**:

   Abra o terminal e execute o comando abaixo (substitua pelo seu e-mail):

   ```bash
   ssh-keygen -t rsa -b 4096 -C "seuemail@exemplo.com"
   ```

   O comando irá gerar uma chave SSH no seu computador. O processo pedirá para você escolher um local para salvar a chave (geralmente, o caminho padrão é o recomendado).

2. **Adicionar a chave SSH ao agente SSH**:

   Após gerar a chave, adicione-a ao agente SSH com os comandos abaixo:

   ```bash
   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_rsa
   ```

3. **Adicionar a chave SSH ao GitHub**:

   - Copie a chave SSH gerada. Você pode usar o comando:

   ```bash
   cat ~/.ssh/id_rsa.pub
   ```

   - Acesse o GitHub, vá para **Settings** e depois em **SSH and GPG keys**.
   - Clique em **New SSH key**, cole a chave copiada e dê um nome a ela.
   - Clique em **Add SSH key**.

4. **Testar a conexão**:

   Para verificar se a chave SSH está configurada corretamente, execute:

   ```bash
   ssh -T git@github.com
   ```

   Se tudo estiver configurado corretamente, você verá uma mensagem de boas-vindas do GitHub, como:

   ```
   Hi username! You've successfully authenticated, but GitHub does not provide shell access.
   ```

---

## 4. Conclusão

Agora você tem o Git instalado e configurado, e sabe como autenticar-se com repositórios remotos usando **token de acesso** ou **chave SSH**. Com isso, você pode começar a versionar seu código e colaborar com outros desenvolvedores utilizando plataformas como **GitHub**.

Se tiver dúvidas ou precisar de mais detalhes, consulte a documentação oficial do [Git](https://git-scm.com/doc) ou do [GitHub](https://docs.github.com/en/github/authenticating-to-github).

