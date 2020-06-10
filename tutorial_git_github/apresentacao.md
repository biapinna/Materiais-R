Usando o Git/Github no RStudio
================
Beatriz Pinna
10/06/20

## Etapas

Este documento apresenta uma breve descrição para você que quer ou
precisa controlar a versão dos seus projetos no R através do Github.
Para isto, vamos seguir estas 3 etapas:

1.  Instalar o Git

2.  Criar uma conta no Github

3.  Controle de Versão no RStudio

## Instalação do Git

Git é um sistema de controle de versões distribuído, usado
principalmente no desenvolvimento de software, mas pode ser usado para
registrar o histórico de edições de qualquer tipo de arquivo. Faça o
download do Git por esse [link](https://git-scm.com/downloads).

Veja se o Git aparece no RStudio em Tools \> Global Optios \> Git/SVN.

<img src="./Images/git_rstudio.png" width="50%" style="display: block; margin: auto;" />

## Conta no Github

Para que você possa controlar o histórico do seu projeto você precisa
criar uma conta gratuita no Github através desse
[link](https://github.com/).

GitHub é uma plataforma de hospedagem de código-fonte com controle de
versão usando o Git. Ele permite que programadores, utilitários ou
qualquer usuário cadastrado na plataforma contribuam em projetos
privados e/ou Open Source de qualquer lugar do mundo.

## Controlde de versão no RStudio

Para configurar o Rstudio com o Git direto pelo RStudio é necessário
instalar o pacote `usethis()`.

``` r
install.packages("usethis")
library(usethis)
```

Após a instalação do pacote, vamos configurar seu e-mail associado ao
Github.

``` r
use_git_config(user.name = "Beatriz Pinna", 
               user.email = "beatrizrpinna@gmail.com") 
```

Agora vamos configurar o Github com o Rstudio. Para isso, vamos criar um
token no Github utilizando a função a seguir.

``` r
browse_github_token()
```

Esta função irá abrir uma página do Github para criar o token. Em
**Note** você poderá atribuir um novo nome e depois clicar em **Generate
Token**. Copie o token gerado e abra o arquivo .Renviron com o comando
abaixo.

``` r
edit_r_environ()
```

No arquivo .Renviron adicione **GITHUB\_PAT=SEU\_TOKEN**, salve o
arquivo e reinicie o RStudio com o comando CTRL + SHIFT + F10. Agora já
podemos trabalhar com projetos no Github clonando um repositório. Para
isso, faça as seguintes etapas:

> Crie um repositório pelo Github

No Github vá em Repositories \> New para criar um novo repositório. Em
**Repository name** coloque o nome que deseja e adicione uma descrição
em **Description**, se quiser. Além disso, é possível escolher a
permissão do seu repositório: público ou privado. Para finalizar,
marque a opção para adicionar o arquivo README, que é uma introdução do
seu projeto e será clonado no seu computador, e clique em **Create
repository**.

<img src="./Images/new_repository.png" width="70%" style="display: block; margin: auto;" />

> Crie um projeto de controle de versão pelo RStudio

No Github abra o repositório que você criou e em **Clone or download**
copie a URL, como aparece na imagem abaixo.

<img src="./Images/clone_repository.png" width="70%" style="display: block; margin: auto;" />

No Rstudio vá em File \> New Project \> Version Control \> Git e crie um
novo projeto de controle de versão. Em **Repository URL** cole o link do
repositório do Github que você copiou. Após inserir o link, o campo
**Project directory name** será prennchido automaticamente, e selecione
o diretório em **Create project as subdirectory of** para salvar a cópia
local do repositório.

<img src="./Images/new_project.png" width="50%" style="display: block; margin: auto;" />

O Git através do RStudio fornece uma interface gráfica simples. Ao abrir
o seu projeto versionados com Git no RStudio você verá o Painel do Git
como na imagem abaixo.

<img src="./Images/painel_git.png" width="50%" style="display: block; margin: auto;" />

É necessário selecionar os arquivos na coluna **Staged** para prosseguir
com o **Commit**. De acordo com a imagem abaixo, primeiro escreva uma
mensagem para identificar o **Commit**, clique no botão commit e
aparecerá uma mensagem dos arquivos modificados, feche a mensagem e
clique em **Push** para subir os arquivos no Github. O comando **Pull**
baixa os códigos no Github para a sua máquina.

<img src="./Images/commit.png" width="90%" style="display: block; margin: auto;" />

Interface gráfica do Rstudio com o Git:

<img src="./Images/git_cheatsheet.png" width="65%" style="display: block; margin: auto;" />
Fonte: [RStudio
Cheatsheet](https://rstudio.com/wp-content/uploads/2016/03/rstudio-IDE-cheatsheet-portuguese.pdf)

## Referências

<https://pt.wikipedia.org/wiki/Git>

<https://pt.wikipedia.org/wiki/GitHub>

<https://beatrizmilz.github.io/RLadies-Git-RStudio-2019/#1>

<https://github.com/saramortara/R-git-apresentacao/blob/master/trabalhos_reprodutiveis.pdf>

<https://www.curso-r.com/blog/2017-07-17-rstudio-e-github/>
