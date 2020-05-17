### Autor: Fábio Delgado

Olá! Seja bem vindo ;)

## Índice
1. [SSIS](#SSIS)
2. [Projeto e Conteúdo](#Projeto-e-Conteudo)
3. [Connection](#Connection)
4. [Conversor](#Conversor)
5. [Fluxo](#Fluxo)
6. [Publicação](#Publicação)
7. [Suporte](#Suporte)

# SSIS(SQL Server Integration Services)

Esse repositorio tem como objetivo apresentar um pouco sobre a arquitetura SSIS(SQL Server Integration Services) que é a ferramenta para projetos de Microsoft ETL. Esse repositorio tem como objetivo apresentar um pouco sobre a arquitetura SSIS(SQL Server Integration Services) que é a ferramenta para projetos de Microsoft ETL. Ele faz parte de um projeto em que implemento uma aplicação por completo (backend, frontend, bases de dados e etcs...)

O SQL Server Integration Services (SSIS) trata-se de um componente do software que é voltado para a integração de informações. Sua especialidade é em relação aos ambientes empresariais, que, mais do que nunca, geram uma grande quantidade de dados. Ou seja, a clássica carga de dados de um repositorio (.csv por exemplo) para o banco de dados.

## Projeto e Conteúdo

Nesse exemplo, é feito uma carga de dados vinda de um arquivo CSV para uma tabela que representa um cadastro de cliente, com informações de nome, email, sexo e cidade.

### Pré-requisitos

![integration](/img/integration.PNG)

Você pode instalar o SQL Server Integration Services nas seguintes configurações:

 - Instalar o SQL Server Integration Services em um computador que não possui instâncias anteriores do SQL Server.
 - Instalar o SQL Server em uma instância existente do Integration Services.
 - Instale o SQL Server Data Tools, para desenvolvimento no visual studio 2017/2019
  - O caminho é Arquivo > Novo > Business Intelligence > Integration Services > Integration Services Project
 
![visualstudio](/img/visualstudio.PNG)

## Connection

O primeiro passo é criar a connection com a base de dados, nesse exemplo a conexão é feita com OLEDB para o banco de dados "CadastroDB". O script para criação das tabelas esta na pasta `script` desse repositório.

![connection](/img/conection.PNG)

Para buscar as informações, disponibilizei um arquivo CSV com dados fake para carga. O delimitador do arquivo é ponto e virgula (;).

![flatfile](/img/flatfile.PNG)

Para facilitar a reutilização de código, criei a parametrização do ETL. Nesse exemplo parametrizei a servername, username e password. Essa parametrização é importante pois, caso a senha do banco de dados mude será necessario alterar apenas um campo parametros e não todas as connections dentro do ETL. É muito comum no ambiente produtivo o analista de suporte ter acesso para alterar o valor dos parametros, facilitando assim as manutenções futuras. 

Para fazer esssa parametriação, clique com o botão direito na connection e clique em "parametrizar".

![parametize](/img/parametize.PNG)

Você pode consultar os parametros na aba da direita "Project-params". É possivel parametrizar na granularidade de projeto ou por DTSX.

![parametros](/img/parametros.PNG)

## Conversor

É muito comum a necessidade de conversão de dados em carga de informações, por exemplo: modelo de data, limitação de tamanho de campo e conversão de encoding. Nesse caso inclui um componente de conversão apenas para exemplificar.

![conversao](/img/conversao.PNG)

## Fluxo

O resultado final fica assim:

![flow](/img/flow.PNG)

O arquivo `data.csv` tem os dados para cadastro da tabela de cliente. Ele contém informações "fake" para representar um ambiente realistico.
O script para criação das tabelas é o `CadastroDB.sql`

![select](/img/select.PNG)

## Publicação

Execute o package file no catálogo de Integration service catalog usando este comando (correspondendo a versão do SQL Server à sua versão instalada):

```shell
dtexec /F Package.dtsx
```

## Suporte

Por favor entre em contato conosco via [Email]