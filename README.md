# Testes Minhas Vendas

*Esse documento possui as informações dos testes de api envolvendo o projeto minhas-vendas*
>Para mais algumas informações não citadas aqui sobre o minhas vendas a documentação se encontra no [bitbucket](https://bitbucket.org/melhor-envio/minhas-vendas/src/master/)
## Para que o que esse documento pode me ajudar?

* *Para os testes de clientes, testes de vendas, webhooks do minhas vendas e testes unitários*

## Instalação 

*Clone o repositório*
```sh
git clone git@bitbucket.org:melhor-envio/minhas-vendas-tests.git
```  
*Instale as depedências*
```sh
composer install
```
## Configurações para o desenvolvimento

*Crie uma cópia do arquivo .env.example e renomeie para .env, informe os valores nas variáveis desejadas. Inclusive nas variáveis de conexão com o banco de dados (necessário para próximo passo)*

```sh
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret
```
*Crie a chave do projeto com o comando:*
```sh
php artisan key:generate
```
*Rode as migrates para criar as tabelas no DB com o comando:*
```sh
php artisan migrate --seed
```
## Configurações para desenvolver os testes

*Crie dois tokens de acesso de api de dois usuários diferentes do Melhorenvio.com.br*
  
>(Para criar vá para Gerenciar/Tokens/Novo Token e coloque os dois tokens no api.suite.yml)
  
 *Configure api.suite.yml para indicar o url(local/develop) onde está o minhas vendas a ser executado.*
   
## Processo de execução dos testes
  
 * *Executar*
```sh
./vendor/bin/codecept run (suite):(test)
```
 * *Adicionar parametro args*
```sh   
suite: (api,acceptance,unit) .Optional
test: (suite):(test) .Optional, Requires suite
```
## Processo de criação de testes Api

* *Criando os testes*
```sh
./vendor/bin/codecept generate:cest (suite) (name) 
```
* *Adicionando parametro args*
```sh
suite: (api,acceptance,unit) .Required
name: (nomedoTeste) .Required
```
## Processo de criação de testes unitários

* *Inserir o comando abaixo na pasta raíz do projeto para rodar os testes.*
```sh
phpunit
```
* *Caso queira rodar uma feature específica, utilize o comando acima com a flag --filter*
```sh
phpunit --filter <nome_do_arquivo>|<nome_do_test>
```
## Acesso local 
* *O path encontra-se na pasta vendor do projeto.*
```sh
./vendor/phpunit/phpunit/phpunit
```
* *Para isso, criamos um script para rodar o mesmo pelo composer:*
```sh
composer phpunit
```
## Responsáveis pelo projeto

[@Eduardo Fischee](https://web.telegram.org/#/im?p=u429962196_13813607528078014522), [@Philippe Bachilli](https://web.telegram.org/#/im?p=u462809362_1310176165730354488) e [@Luan Einhardt](https://web.telegram.org/#/im?p=@luaneinhardt)

## Contribuindo

1. Faça o _fork_ do projeto (<https://github.com/yourname/melhor-envio/minhas-vendas-tests/fork>)
2. Crie uma _branch_ para sua modificação (`git checkout -b feature/minhas-vendas-tests)
3. Faça o _commit_ (`git commit -am 'Add um novo teste api'`)
4. _Push_ (`git push origin feature/teste api`)
5. Crie um novo _Pull Request_
