## 1. Qual a diferença entre Git e GitHub?

**Resposta**:  
- **Git** é um **Sistema de Controle de Versão Distribuído (DVCS)** utilizado para rastrear mudanças no código-fonte.  
- **GitHub** é uma plataforma online que utiliza o Git para hospedar repositórios e permitir colaboração entre desenvolvedores.

---

## 2. Qual comando utilizado no Git para enviar alterações do repositório local para o remoto?

**Resposta**:  
O comando utilizado é:

```bash
git push
```

Este comando envia as alterações feitas no repositório local para o repositório remoto.

---

## 3. Qual comando do Git podemos utilizar para alterar a mensagem de um commit?

**Resposta**:  
O comando para alterar a mensagem do último commit é:

```bash
git commit --amend -m "nova mensagem"
```

Isso permite modificar a mensagem do commit mais recente.

---

## 4. Qual comando do Git podemos utilizar para alternar entre branches?

**Resposta**:  
O comando para alternar entre branches é:

```bash
git checkout <nome-da-branch>
```

A partir do Git 2.23, também é possível usar o comando `git switch` para realizar a mesma operação.

---

## 5. Qual comando utilizado para configurar o email no Git?

**Resposta**:  
O comando para configurar o email no Git é:

```bash
git config --global user.email "seuemail@exemplo.com"
```

Este comando define o email associado aos commits no Git.

---

## 6. Qual comando utilizado para clonar apenas uma branch?

**Resposta**:  
O comando para clonar apenas uma branch é:

```bash
git clone <url> --branch <nome-da-branch> --single-branch
```

Este comando clona apenas a branch especificada do repositório remoto.

---

## 7. Qual o comando utilizado para criar uma cópia de um repositório Git existente?

**Resposta**:  
O comando para criar uma cópia de um repositório Git existente é:

```bash
git clone <url-do-repositorio>
```

Isso cria uma cópia local do repositório remoto.

---

## 8. Sobre Versionamento de Código, é INCORRETO afirmar:  
**Resposta**:  
"**Gera uma nova versão do código somente ao final do desenvolvimento de cada projeto**" é **incorreto**.

O versionamento de código é feito **ao longo do desenvolvimento**, com **commits** constantes que registram mudanças incrementais no código.

---

## 9. Qual comando do Git podemos utilizar para ver o histórico de commits?

**Resposta**:  
O comando utilizado para ver o histórico de commits é:

```bash
git log
```

Esse comando exibe um histórico dos commits feitos no repositório.

---

## 10. Qual comando podemos utilizar para ver as diferenças entre a versão local e a versão remota?

**Resposta**:  
O comando utilizado para ver as diferenças entre a versão local e a versão remota é:

```bash
git diff
```

Esse comando exibe as diferenças entre os arquivos locais e os arquivos no repositório remoto ou entre diferentes commits.

---

### Conclusão

Esses comandos são fundamentais para trabalhar com Git, ajudando a gerenciar versões e colaborar em projetos de desenvolvimento. Com o tempo, você aprenderá a usar esses comandos de forma mais eficiente e a explorar outras funcionalidades avançadas do Git.

Se você tiver dúvidas ou precisar de mais detalhes, fique à vontade para consultar a documentação oficial do [Git](https://git-scm.com/doc) ou pedir ajuda! 🚀

---

Espero que esse README seja útil! Se precisar de ajustes ou mais informações, é só falar! 😊