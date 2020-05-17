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

![integration](/img/integration.PNG)

## Connection

![conection](/img/conection.PNG)

## Conversor

![conversao](/img/conversao.PNG)

## Fluxo

![flow](/img/flow.PNG)

O arquivo 'data.csv' tem os dados para cadastro da tabela de cliente. Ele contém informações "fake" para representar um ambiente realistico.
O script para criação das tabelas é o 'CadastroDB.sql'

![select](/img/select.PNG)

## Publicação

Execute o package file no catálogo de Integration service catalog usando este comando (correspondendo a versão do SQL Server à sua versão instalada):

```shell
dtexec /F Package.dtsx
```

## Suporte

Por favor entre em contato conosco via [Email]