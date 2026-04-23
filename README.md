# TDDSoftware

Projeto desenvolvido durante a atividade de Testes de Software com Django e Selenium, seguindo o roteiro da Aula Prática 02. A proposta foi evoluir uma aplicação simples de lista de tarefas usando o ciclo de TDD.

## Objetivo

O objetivo do projeto é demonstrar a evolução de uma aplicação inicialmente estática para uma aplicação web dinâmica. Durante a atividade, a página inicial passou a usar templates, formulário com método POST, processamento de requisições, persistência em banco de dados e testes automatizados.

## Tecnologias Utilizadas

- Python
- Django
- Selenium 4
- SQLite
- unittest

## Funcionalidades

- Exibe uma página inicial para uma lista de tarefas.
- Permite adicionar novos itens por meio de um formulário.
- Salva os itens no banco de dados usando model do Django.
- Lista todos os itens cadastrados na página inicial.
- Usa enumeração nos itens exibidos.

## Estrutura Principal

- `functional_tests.py`: teste funcional com Selenium, simulando o uso da aplicação pelo usuário.
- `lists/tests.py`: testes de unidade e integração da aplicação.
- `lists/views.py`: view principal responsável por processar requisições e renderizar o template.
- `lists/models.py`: model `Item`, usado para armazenar os itens da lista.
- `lists/templates/home.html`: template HTML da página inicial.
- `lists/migrations/`: migrations usadas para criar e atualizar a estrutura do banco de dados.

## Como Executar o Projeto

Instale as dependências necessárias e execute as migrations:

```bash
python manage.py migrate
```

Inicie o servidor Django:

```bash
python manage.py runserver
```

Acesse a aplicação em:

```text
http://localhost:8000
```

## Como Rodar os Testes

Para rodar os testes de unidade:

```bash
python manage.py test
```

Para rodar o teste funcional com Selenium, mantenha o servidor Django rodando em outro terminal:

```bash
python functional_tests.py
```

Observação: o teste funcional usa o banco de dados local. Se já existirem itens cadastrados de execuções anteriores, o resultado pode ser afetado. Nesse caso, limpe o banco e aplique as migrations novamente antes de rodar o teste funcional.

## Sobre o Processo TDD

O desenvolvimento seguiu o ciclo de TDD: escrever um teste, executar o teste para ver a falha esperada, implementar a solução mais simples possível e rodar os testes novamente. Os testes funcionais verificaram o comportamento da aplicação do ponto de vista do usuário, enquanto os testes de unidade ajudaram a guiar as pequenas alterações internas no código.
