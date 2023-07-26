# Teste DevOps

Criando um projeto simples para o curso de DevOps.

---

## **Será que foi?!**

[x] Sim!!

---

## Comandos Git + Usados

### **1. Git clone**

Git clone é uma comando para baixar o código-fonte existente de um repositório remoto.

`git clone <https://link-com-o-nome-do-repositório>`


### **2. Git branch**

*Branches* (ramificações, em português) são altamente importantes no mundo do git. Usando as  *branches* , vários desenvolvedores conseguem trabalhar em paralelo no mesmo projeto simultaneamente.

#### ****C**omo criar uma** branch:****

```
git branch <nome-da-branch>
```

Para fazer o push da nova branch para o repositório remoto, você precisa usar o comando a seguir:

```
git push -u <local-remoto> <nome-da-branch>
```


#### **Como ver as **branches:****

```
git branch ou git branch --list
```


#### **Como excluir um**a branch:

```
git branch -d <nome-da-branch>
```


### **3. Git checkout**

Usado para trocar de uma branch para outra. Também podemos usar o comando para fazer o checkout de arquivos e commits.

```
git checkout <nome-da-branch>
```

Existem alguns passos que você precisa seguir para trocar de branch com sucesso:

* As alterações em sua branch atual devem estar em um commit ou em um stash antes de você fazer a troca;
* A branch na qual você quer fazer o checkout deve existir no seu espaço de trabalho local.

**Também existe um comando de atalho que permite criar e automaticamente trocar para a** branch **criada ao mesmo tempo**:

```
git checkout -b <nome-da-branch>
```

Esse comando cria a branch em seu espaço de trabalho local (a flag -b representa a branch) e faz o checkout na nova branch logo após sua criação.


### **4. Git status**

O comando git status nos dá todas as informações necessárias sobre a branch atual.

```
git status
```

Obtemos as seguintes informações:

* Se a branch em que estamos no momento está atualizada;
* Se precisamos fazer o commit, push ou pull de algo;
* Se os arquivos estão em fase de stage, fora dessa fase ou se não estão sendo rastreados; e
* Se arquivos foram criados, modificados ou excluídos.

### **5. Git add**

Incluir as alterações de um ou vários arquivos em nosso próximo commit.

**Para adicionar um único arquivo**:

```
git add <arquivo>
```

**Para adicionar tudo ao mesmo tempo**:

```
git add -A
```

***Important**e*: o comando **git add** não altera o repositório. As alterações não são salvas até que se use **o **git commit.****


### **6. Git commit**

Defini um ponto de verificação no processo de desenvolvimento, onde você pode voltar a esse ponto mais tarde, se necessário.

Apresenta uma breve descrição para explicar o que desenvolvemos ou alteramos no código-fonte.

```
git commit -m "mensagem do commit"
```

**Important**e: **git commit** salva suas alterações no espaço de trabalho **local.**


### **7. Git push**

Envia as alterações ao servidor remoto. **Git push** faz o upload dos seus commits no repositório remoto.

```
git push <repositório-remoto> <nome-da-branch>
```

Entretanto, se a sua branch foi recém-criada, também é preciso fazer o upload da branch com o seguinte comando:

```
git push --set-upstream <repositório-remoto> <nome-da-branch>
```

ou

```
git push -u origin <nome-da-branch>
```

****Important**e**: **g**it push **somente faz o **upload** das alterações que já estão em um** commit.****


### **8. Git pull**

Usado para obter as atualizações de um repositório remoto. Esse comando é uma combinação de ****git fetch**** e  ****git merge**** . O comando git pull, recebe as atualizações do repositório remoto (git fetch) e aplica imediatamente as alterações mais recentes em seu espaço de trabalho local (git merge).

```
git pull <repositório-remoto>
```

**Essa operação *pode* causar conflitos que você precisará resolver **manual**mente**.


### **9. Git revert**

Desfazer as alterações que fizemos. Esse comando é uma maneira segura de desfazer nossos commits. Para ver nosso histórico de commits, primeiro, precisamos usar ****git log -- oneline:****

`git log [<options>] [<revision-range>] [[--] <path>…]`

Em seguida, precisamos apenas especificar o código hash ao lado do commit que desejamos desfazer:

```
git revert 3321844
```

Depois disso, basta pressionar ****shift + q**** para sair.

O comando git revert desfará o commit especificado, mas criará outro commit sem excluir o antigo.

A vantagem de se usar ****git revert**** é não tocar no histórico de commits. Isso significa que você ainda pode ver todos os commits do seu histórico, mesmo os revertidos.

Outra medida de segurança está no fato de que tudo acontece em nosso sistema local, a menos que façamos o push de tudo para o repositório remoto. É por isso que o uso de **git revert** é mais seguro e é a forma preferida de desfazer nossos commits.


### **10. Git merge**

É a etapa final, fazer o merge (mesclar ou unir, em português) da branch com a branch pai (dev ou master/main, em geral). Isso é feito com o comando `git merge`.

Basicamente, integra sua **branch** com o recurso e todos os seus **commits** na **branch** de desenvolvimento (dev) ou na **branch principal** (*master* ou *main*). É importante lembrar que, primeiro, você precisa estar na **branch específica** na qual você quer fazer o **merge** de sua **branch** com o recurso.

Por ***exemplo***, ao querer fazer o merge de sua branch do recurso na branch dev:

**Primeiro, troque para a branch  **dev** :**

```
git checkout dev
```

**Antes do **merg**e**, atualize sua branch dev  **local** :

```
git fetch
```

**Por fim**, faça o merge **da sua **branch **do recurso em** dev:****

```
git merge <nome-da-branch-com-o-recurso>
```

**Dica**: **certifique-se de que sua branch** dev **tem a versão mais recente antes de fazer o **merge **de suas** branches** de recurso. Do contrário, você pode ter que lidar com conflitos e outros problemas indesejados**.

Esses são os meus 10 comandos mais usados do Git.
