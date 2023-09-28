# Estudos em NodeJS API
Nesta seção, documentarei meu progresso e aprendizado no módulo "NodeJS API escalável com e sem Express".
Deixarei também os comandos utilizados durante todo o módulo, como forma de consulta e principalmente para estudos pessoais.
Tópicos vistos durante o módulo:
1. Introdução
2. Iniciando o projeto
3. Adicionando Types
4. Instalando o banco de dados
5. Criando modelagem
6. Conectando ao banco
7. Criando usuário
8. Criptografando senha
9. Autenticação
10. Organizando rotas
11. Criando repository
12. Divisão de responsabilidades
13. Criando Vídeo
14. Pegando vídeos do usuário
15. Pesquisando vídeos
16. Autenticação nas rotas
17. Upload de arquivos
18. Variáveis de ambiente
19. Gerando build

API criada usando o Postman
![image](https://github.com/igoralexandria/nodejs_api_escalavel/assets/105749982/42a6a1c7-a067-49ef-8aa9-33ec4fd20b5b)

Tabelas de "users" e "videos" com seus respectivos valores de teste. - Usando o MySQL Workbench
![image](https://github.com/igoralexandria/nodejs_api_escalavel/assets/105749982/9698e14c-0973-4dbb-a5dc-9eb303cbb541)
![image](https://github.com/igoralexandria/nodejs_api_escalavel/assets/105749982/30a5ddc1-ebbb-446a-975d-c378c11218fd)

Comandos utilizados:

npm init -> Iniciar um projeto node criando o arquivo package.json. Adicionando a flag "-y" depois do npm init, ele responde de forma automática as perguntas feitas. -> npm init -y

npm i express (dependência express) -> Serve para gerenciar rotas e criar o servidor

node .\src\servidor.js -> rodar o servidor por meio de um arquivo

npm i nodemon -D -> Utilizar somente em desenvolvimento

Ao adicionar o "dev": "nodemon src/server.js" no arquivo package.json você está trocando o modo como executamos o servidor. Deixando de ser "node .\src\servidor.js" para "npm run dev". Agora, a aplicação executa em tempo real, sem precisar parar o servidor ao realizar alterações.

Adicionando/Convertendo o projeto para TypeScript: Por padrão o node.js não consegue ler arquivos typescript.
1º Mudar o arquivo "server.js" para "server.ts".
2º npm i ts-node-dev -D -> Em vez de utilizar o nodemon que estávamos utilizando anteriormente, agora iremos utilizar o ts-node-dev para rodar a aplicação. Logo, basta mudar as alterações no arquivo package.json: "dev": "nodemon src/server.js" para "dev": "ts-node-dev src/server.ts".

npm i @types/express -D -> Adicionando dependência para o express

npm i mysql -> Instalar os pacotes do mysql na aplicação
npm i @types/mysql -D -> Instalando suas dependências

npm i uuid -> Essa biblioteca é responsável por criar ids únicos

npm i bcrypt -> Senha responsável por criptografar senha e inserir no banco
npm i @types/bcrypt -D -> Instalando suas dependências

npm i jsonwebtoken -> Responsável por gerar um token criptografado para o usuário acessar a página, podendo até atribuir um tempo de validação do token (1h, 8h, 1d)
npm i @types/jsonwebtoken -> Instalando suas dependências

npm i dotenv -> Para trabalharmos com variáveis de ambiente

npm i typescript -D -> Por padrão o nodeJS não reconhece o TypeScript. Podemos utilizar só em desenvolvimento, mas em produção pegamos todo a parte de TypeScript e transformamos para JavaScript
npx tsc --init -> Pacote externo que basicamente ele vai criar um arquivo de configuração do TypeScript.

Após ter executado o --init e ter modificado o "outDir": "./dist", basta executar o npx tsc para criar a pasta dist.
Lembrar de configurar o arquivo "package.json" e adicionar no Debug os valores -> "build": "npx tsc" e "start": "node ./dist/server.js"

Caso a dist seja apagada, deve-se rodar no terminal os comandos: "npm run build" e "npm start"

Recaptulando: Basicamente pegamos todo nosso projeto que antes estava em TypeScript, convertermos em JavaScript dentro da past "dist" e depois criamos dois scripts -> O "build" para caso precisaremos criar novamente a pasta e uma possível alteração, e o "start" para rodar a aplicação.
