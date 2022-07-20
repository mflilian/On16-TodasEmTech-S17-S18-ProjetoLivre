*Dependências que utilizamos*
______________________________

COMUNS - pasta raiz (fora de SRC)
(Repositorio: 
1 - https://github.com/reprograma/On16-TodasEmTech-S8-API-Get-Post
2- https://github.com/reprograma/On16-TodasEmTech-S9-API-Delete-Post-Put-Patch
3 - https://github.com/reprograma/On16-TodasEmTech-S10-Projeto-2-CRUD)

*Package*
npm init -y

*Express.js - node_modules*
npm i express cors

*Nodemon*
npm i -D nodemon

BANCO DE DADOS
(repositório : 
1- https://github.com/reprograma/On16-TodasEmTech-S12-Intro-BD
2- https://github.com/reprograma/On16-TodasEmTech-S13-Projeto-3-CRUD-BD)

*Mongoose - mongodb*
npm i mongoose

SEGURANÇA - AUTH
(repositório: https://github.com/reprograma/On16-TodasEmTech-S14-Auth)

*Jwt*
npm install jsonwebtoken -- save
*Bcrypt*
npm install bcrypt -- save
*Dotenv*
npm install dotenv-safe -- save


AUTOMAÇÃO \ TESTES
(repositorio: https://github.com/reprograma/On16-TodasEmTech-S15-Automacao-Testes)

*ESlint*
npm install --save-dev eslint@8.16.0
npx eslint --init

**Escolhas do ESlint**
How would you like to use ESLint? · style
What type of modules does your project use? · commonjs
Which framework does your project use? · none
Does your project use Type? · No
Where does your code run? · node
How would you like to define a style for your project? · guide
Which style guide do you want to follow? · airbnb
What format do you want your config file to be in? · JSON
Would you like to install them now? · Yes
Which package manager do you want to use? · npm

*Jest*
npm install --save-exact jest@28.1.0 

--

*Swagger* (dentro da pasta raiz) 
(repositorio https://github.com/reprograma/On16-TodasEmTech-S17-S18-ProjetoLivre)
***parte_1***
 npm i swagger-autogen swagger-ui-express (isso fará a instalacao do swagger autogen no nosso projeto)
 touch swagger.js (isso fará com que um arquivo swagger seja criado no nosso projeto)
 mkdir swagger/  (isso fará com que uma pasta swagger seja criada no nosso projeto)
***parte_2*** 
no arquivo swagger.js e adicionamos esse pedaço de código:

const swaggerAutogen = require('swagger-autogen')();
     const outputFile = './swagger/swagger_output.json';
     const endpointsFiles = ['./src/app.js'];
     swaggerAutogen(outputFile, endpointsFiles);

***parte_3*** 
no nosso package.json:
"”: {
   "start": "nodemon server.js",
   "swagger-autogen": "node swagger.js",
 }

***parte_4*** 
no terminal:
npm run swagger-autogen

***parte_5*** 
no nosso app.js e adicionaremos o seguinte código:
    const swaggerFile = require('../swagger/swagger_output.json');
    app.use('/minha-rota-de-documentacao', swaggerUi.serve, swaggerUi.setup(swaggerFile));

***parte6*** 
no terminal: npm start

***parte_7*** 
acessaremos a nossa rota

localhost:3000/minha-rota-de-documentacao

PS: Estou usando a porta 3000, caso vc esteja usando alguma diferente, use ela, beleza?


-------------------------------------------------------------------------------
ARQUITETURA MVC - EXEMPLO (adapte para o seu projeto)

  📁 PROJETOFINAL (essa é a pasta raiz) 
  | 
  |-  📁 node_modules ( dentro da pasta raiz)
  |
  |-  📁 Swagger (dentro da pasta raiz)
  |         |- 📄 Swagger.json 
  |
  |-  📁 src (dentro da pasta raiz)
  |    |
  |    |- 📁 database  (dentro src)
  |         |- 📄 mongooseConnect.js  
  |
  |    |- 📁 controllers  (dentro src)
  |         |- 📄 xController.js  
  |         |- 📄 yController.js  
  |  
  |    |- 📁 models (dentro src)
  |         |- 📄 xModel.js  
  |         |- 📄 yModel.js  
  |  
  |    |- 📁 routes  (dentro src)
  |         |- 📄 xRoutes.js   
  |         |- 📄 yRoutes.js 
  |
  |    |- 📁 test (dentro src)
  |         |- 📄 x.test.js
  |
  |    |- 📄 app.js (dentro src)
  |
  |- 📄 Procfile (pasta raiz - esse é o heroku gatinhas)
  |- 📄 Swagger.js (pasta raiz)
  |- 📄 .eslintrc (pasta raiz) - surge depois de *Escolhas do ESlint* (instalação acima))
  |- 📄 .env (pasta raiz
  |- 📄 .env.example (pasta raiz)
  |- 📄 .gitignore  (pasta raiz)
  |- 📄 package-lock.json  (pasta raiz)
  |- 📄 pakage.json (pasta raiz)
  |- 📄 README.md  (pasta raiz)
  |- 📄 server.js  (pasta raiz)





GENTE AQUI ESTÁ O LINK PARA GERAR SENHA DE SEGURANÇA, A SECRET OK?
https://passwordsgenerator.net/sha1-hash-generator/






