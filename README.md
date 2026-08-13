# Guia de Versionamento e Colaboração da XPTO
* Nomes:
  Caroline de Carvalho Mendes        RA: 2171392511041
  Priscila de Carvalho Mendes        RA: 2171392511039
* Período: Matutino
* Ciclo: 4 Semestre
* Curso: Desenvolvimento de Software Multiplataforma

## Fluxo de trabalho

O desenvolvimento é realizado utilizando branches, commits e Pull Requests para garantir organização e revisão das alterações.

### Guia de Versionamento e Colaboração da XPTO
#### Passo 1. Objetivo

Orientar um novo desenvolvedor desde a obtenção do projeto até a integração de suas alterações à branch principal.


#### Passo 2. Obtenção do projeto

Para começar, o desenvolvedor deve clonar o repositório para seu computador.
```bash
git clone URL_DO_REPOSITORIO

````
Depois de clonar, é possível verificar a situação do repositório com:
```bash
git status

````

#### Passo 3. Criar uma branch para a alteração

Uma branch é uma linha de desenvolvimento independente que permite desenvolver funcionalidades separadamente.
```bash
git checkout -b feature-login
````
O uso de branches para funcionalidades e a prática de evitar commits diretos na main são recomendações apresentadas no material.


#### Passo 4. Desenvolver e testar a alteração

Com a branch criada, o desenvolvedor realiza as modificações necessárias no código.

Durante o desenvolvimento, é essencial verificar o estado do projeto atual:
```bash
git status
````
Quando as alterações estiverem totalmente prontas, os arquivos devem ser adicionados ao staging:
```bash
git add .
````
Também é possível adicionar somente um arquivo:
```bash
git add arquivo.txt
````


#### Passo 5. Criar um commit

Depois de adicionar os arquivos ao staging, deve ser criado um commit.
```bash
git commit -m "Implementa tela de login"
````
O commit registra uma alteração no projeto e possui identificador único, autor, data e mensagem descritiva.

O histórico pode ser consultado com:
```bash
git log
````


#### Passo 6. Enviar a branch para o GitHub

Após realizar o commit, a branch deve ser enviada para o repositório remoto:
```bash
git push origin feature-login
````
Na primeira vez, também pode ser utilizado:
```bash
git push -u origin feature-login
````
O push envia as alterações para o GitHub.


#### Passo 7. Criar um Pull Request

A integração das alterações normalmente acontece por meio de um Pull Request (PR) no GitHub

O PR deve ter:

Base: main
Compare: branch de desenvolvimento, como feature-login


#### Passo 8. Pipeline de CI/CD

Quando ocorre um push ou um Pull Request direcionado à main, a pipeline pode ser executada automaticamente.

O fluxo é:

Push

  |
  
Build
  |
Testes
  |
Aprovação
  |
Deploy

Cada etapa possui uma função:

Build: verifica se é possível gerar o artefato.
Testes: verifica se o comportamento está correto.
Deploy: verifica se o sistema pode ser entregue com segurança.


#### Passo 9. Revisão e integração na main

Após a criação do Pull Request, as alterações devem ser analisadas pela equipe. Se a revisão e as validações necessárias forem concluídas, o PR pode ser integrado à main.

O merge é o processo responsável por combinar duas branches e integrar as alterações ao projeto principal.

Em um fluxo colaborativo, portanto:

feature-login
      |
Pull Request
      |
Revisão + Pipeline
      |
Merge
      |
main


10. Atualizar o projeto local

Depois que alterações forem integradas à main, os desenvolvedores devem manter seus repositórios locais atualizados.

Para trazer as alterações do repositório remoto:
```bash
git pull
````
Ou:
```bash
git pull origin main
````

11. Desfazendo uma alteração

Caso seja necessário desfazer um commit, a XPTO pode utilizar:
```bash
git log --oneline
git revert HASH_DO_COMMIT
````
12. Fluxo da XPTO

O fluxo completo de desenvolvimento é:

1. Clonar o repositório
          |
2. Criar uma branch
          |
3. Editar/desenvolver o código
          |
4. git add
          |
5. git commit
          |
6. git push
          |
7. Criar Pull Request
          |
8. Revisão e execução da pipeline
          |
9. Merge na main
          |
10. git pull para atualizar o projeto local
