Wordpress + SQLite no Openshift
======================

Este repositório git lhe ajuda a configurar e instalar o Wordpress de maneira rápida.
O propósito é atendar à necessidade de aplicações não-escaláveis que necessitem de performance
para rodar em gears pequenos (menor que 1GB).

O backend de banco de dados é o SQLite3, utilizado através do plugin [sqlite-integration](https://wordpress.org/plugins/sqlite-integration/).
**Alguns plugins não funcionam com este repositório**. Veja aqui a [lista de incompatibilidades](http://dogwood.skr.jp/wordpress/sqlite-integration/#index-plugin-compat) e os [plugins alternativos](http://dogwood.skr.jp/wordpress/sqlite-integration/#index-substitutions).

Criando a aplicação:
--------------------

Crie uma conta em http://getupcloud.com e [instale o RHC](https://getup.zendesk.com/entries/38781627)

Crie uma aplicação php-5.4

    rhc app create [NOME] php-5.4 --from-code=https://github.com/caruccio/wordpress-sqlite

Pronto, basta acessar a url e finalizar a instalação:

    http://[NOME]-$namespace.getup.io
