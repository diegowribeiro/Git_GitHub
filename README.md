# Introdução ao Git e GitHub 

## O que é Git?
Git é um sistema de controle de versões, trata-se de um "orquestrador" e organizador de código fonte, é possível desenvolver um projeto da linguagem que for, por diversas pessoas "codando" e colaborando no mesmo projeto. É a melhor forma de manter a integridade, rastreabilidade do desenvolvimento de um projeto e até mesmo para casos de erro é possível voltar ao estado anterior que desejar, graças á um sistema de snapshot que tira uma "foto" em todos os momentos que ocorre uma alteração, tudo isso realizado de forma automática é nativo, funciona!!!.

Há muito tempo conhecido e utilizado pelos desenvolvedores (ou pelo menos a maioria, por que já vi alguns trabalhando com versionamento _Old_) porém desconhecido até "pouco tempo" para a galera de Infra/Sysadmin/operações, eu por exemplo sou um deles. Com essa onda de Devops, resolvi surfar nesta onda e confesso que é bem maior do que pensei e por esse motivo está me fazendo estudar muito, aprender muito e evoluir de mais... estou pisando em terrenos(Dev) que jamais imaginei e confesso que estou curtindo.

## O que é GitHub?
O GitHub é uma plataforma Web que você pode armazenar diversos projetos gratuitamente e compartilhar com a comunidade para que todos possam colaborar, tem a opção de ter repositórios privados e compartilhar apenas com quem determinar, porém essa modalidade é paga. Inúmeros projetos open source estão hospedados no GitHub e qualquer um pode colaborar, como do kernel do Linux por exemplo(https://github.com/torvalds/linux).

## Instalação do Git
Explicado a parte mais burocrática, vamos começar a colocar a mão na massa...

Instalação no Fedora:
$ sudo dnf install git-all

Instalação Debian e derivados:
$ sudo apt-get install git-all

Instalação em outros SO's ou mais detalhes, acesse link:
https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

## Acesso ao GitHub
Aproveitando que estamos na pegada, crie uma conta no GitHub(https://github.com/) não vou detalhar, pois é muito simples(Nome, e-mail).
Já com a conta criada de cara vai ter a opção "Create a new repository", crie com o nome que desejar:

<img width="731" alt="captura de tela 2017-09-14 as 20 23 21" src="https://user-images.githubusercontent.com/24530268/30460089-07c3f7e8-998b-11e7-851c-1925d1c28431.png">

Neste exemplo criei um projeto chamado "My_eccomerce" e você poderá acessar seu projeto através da url: https://github.com/<username>/projeto e no meu caso ficou assim: https://github.com/diegowribeiro/My_eccomerce
  
OBS: Ao criar um projeto, é preciso ter um arquivo "README.md" trata-se da descrição do seu projeto, caso esteja procurando colaboradores para o seu projeto... neste momento que pode "vender"seu peixe e seria muito interessante colocar em ingles para atingir o maior número de pessoas possíveis.

## Interação com o Git

Até aqui instalamos o git e criamos uma conta no GitHub e criamos nosso projeto, agorá vamos configurar o git e começar a interagir com nosso novo projeto. Neste caso estou utilizando uma máquina linux, por tanto só vai rolar linha de comando...

Já na sua máquina, os dois comandos a seguir vai configurar seu nome e e-mail para assim temos uma configuração simplificada para depois conseguir interagir com o GitHub.
git config --global user.name "Seu Nome"
git config --global user.email "Seu Email"

Agora vamos "puxar" o projeto que criamos no Github para nossa máquina local, para isso basta pegar a url no padrão já mencionado e acrescentar .git ao final ou então no GitHub acessar a página principal do projeto e ir na opção "clone or download" conforme imagem mais abaixo. 

No meu caso ficou assim: https://github.com/diegowribeiro/My_eccomerce.git

<img width="1013" alt="captura de tela 2017-09-14 as 20 47 29" src="https://user-images.githubusercontent.com/24530268/30460571-0307c04c-998e-11e7-8be8-2409501815c0.png">

Execute o comando "clone" o comando é sugestivo...
git clone https://github.com/diegowribeiro/My_eccomerce.git

<img width="692" alt="captura de tela 2017-09-14 as 20 54 23" src="https://user-images.githubusercontent.com/2453

Pronto! já tem o projeto em sua máquina e pode começar a trabalhar nele... por ser um projeto publico, qualquer pessoa pode baixar seu projeto e "trabalhar nele" porém só conseguem realizar modificações no seu projeto raiz se você permitir, caso contrário somente o dono consegue modificar de forma explícita.

Alguns comandos que você precisa dominar para interagir com o git:
<pre class="prettyprint">
    <code class="lang-bsh">$ git add aqr - faz com que o Git reconheça determinado arquivo, não realiza o upload ao projeto por exemplo</code>
</pre>
<pre class="prettyprint">
    <code class="lang-bsh">$ git commit -m "Mensagem Identificação" - Esse comando diz que o arquivo que adicionou anteriormente está pronto, e pode--se adicionar uma mensagem para identificar do que se trata</code>
</pre>
<pre class="prettyprint">
    <code class="lang-bsh">$  git push - Comando que de fato realiza o "upload" do arquivo para o GitHub neste caso.
</code>
</pre>
<pre class="prettyprint">
    <code class="lang-bsh"> git status - Mostra o status do seu repositório.</code>
</pre>
 
  
## Interagindo com o Projeto

Como já colocamos o projeto, dentro do diretorio correspondente vou criar um arquivo index.html para criar a página do meu ecommerce.

<img width="460" alt="captura de tela 2017-09-14 as 21 16 23" src="https://user-images.githubusercontent.com/24530268/30461107-11924afc-9992-11e7-9ada-2595f9eedfae.png">

Após criar o arquivo, execute o comando "git status":

<img width="542" alt="captura de tela 2017-09-14 as 21 18 26" src="https://user-images.githubusercontent.com/24530268/30461143-555e6888-9992-11e7-96f9-dc2b9c8c4940.png">

O próprio git diz que tem um novo arquivo, porém ele não reconhece e logo te dá a sugestão de adicionar esse arquivo com o comando que já vimos "git add", muito esperto esse git não?

Então, conforme orientado... executei o comando para adicionar e novamente verificar o status e olha que bonito, agora ele reconhece o arquivo:

<img width="481" alt="captura de tela 2017-09-14 as 21 21 39" src="https://user-images.githubusercontent.com/24530268/30461177-c42a0a74-9992-11e7-9852-75a37c250486.png">

Adicionado o arquivo, precisamos "commitar" pois só assim "salva" de fato o arquivo e em seguida já vou realizar o "push" para o GitHub:

<img width="676" alt="captura de tela 2017-09-14 as 21 29 46" src="https://user-images.githubusercontent.com/24530268/30461314-e4b6a710-9993-11e7-9d6f-529f01c9d59c.png">

Realizado o commit e o push com sucesso, repare que na hora que realizei o "push" ele pediu o usuário e senha do GitHub é possível configurar para ir direto, sem solicitar essas informações mas por hora vamos tocar desta forma.

Acessando a página do projeto lá no GitHub é possível ver o arquivo que criei:

<img width="1017" alt="captura de tela 2017-09-14 as 21 33 46" src="https://user-images.githubusercontent.com/24530268/30461398-7419cfa4-9994-11e7-8577-1a3f763f19c3.png">

Só para verificar como funciona a cada incremento, siga os mesmo passos até o "push" adicionando um conteúdo ao "index.html":

<img width="475" alt="captura de tela 2017-09-14 as 21 51 03" src="https://user-images.githubusercontent.com/24530268/30461718-e354d7ea-9996-11e7-8b02-d8f604141527.png">


Após seguir todos os passo e enviar para o GitHub, acesse novamente a interface do projeto selecione o arquivo "index.html" > "History" e seleciona e a alteração realizada no arquivo. Desta forma é destacado somente o que foi alterado nesta etapa:

<img width="1004" alt="captura de tela 2017-09-14 as 21 55 31" src="https://user-images.githubusercontent.com/24530268/30461815-81ee5cc8-9997-11e7-8ca5-bfa11d146017.png">

Nesta hora que entra o comando para trabalhar com aqueles snapshots que comentei la em cima... existe mais de uma opção mais a mais "segura" é o "git revert" que é possível passar o parâmetro tag que volta exatamente para o estado que deseja.

Nesta imagem é possível verificar as "tags"criadas no meu projeto "My ecommerce", repare o quanto é importante documentar certinho, colocar mensagens do "commit" que faz sentido... até na hora de reverter facilita.

<img width="989" alt="captura de tela 2017-09-14 as 22 15 01" src="https://user-images.githubusercontent.com/24530268/30462157-3c8fdf5a-999a-11e7-9f9f-4a1c74b38c99.png">

Por último, um comando que facilita a vida é o "git pull" com esse comando é possível atualizar o seu repositório local, imagina que tem uma equipe trabalhando no projeto a galera realizou diversas alterações no projeto e você chega no dia seguinte para trabalhar, é preciso atualizar seu repositório local a fim de evoluir o projeto... se executar o comando "git clone" vai dar erro dizendo que o projeto já existe ou se fizer em outro local todos os dias terá diversas cópias do projeto. Nesta hora que entra o git pull, ele simplesmente "sincroniza" tudo que tem no repositório e vida que segue.

Nessa pegada, você consegue desenvolver seu sistema/projeto com o seu time centralizado em um repositório onde todos tem acesso facilmente garantindo a integridade.

Vou ficando por aqui, ainda neste mesmo tema tem questão de boas práticas para "branch" e "Git Flow" tem outros assuntos para um projeto evoluir de forma espetacular com CI/CD, mas isso é muito assunto e ainda alguns posts, até o próximo.
