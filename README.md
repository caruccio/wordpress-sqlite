Wordpress no Openshift
======================

Este repositório git lhe ajuda a configurar e instalar o Wordpress de maneira rápida.
O propósito é atendar a necessidade de aplicação não-escaláveis que precisem de performance
para rodar em gears pequenos (menor que 1GB).

O backend de banco de dados é o SQLite3, utilizado através do plugin [sqlite-integration](https://wordpress.org/plugins/sqlite-integration/).

Você poderá dar o nome que quiser para sua aplicação, entretanto, o nome da base de dados sempre será correspondente ao nome da aplicação.

Criado a aplicação:
----------------------------

Crie uma conta em http://getupcloud.com e instale o CLI ( veja aqui: https://getup.zendesk.com/entries/38781627 )

Crie uma aplicação php-5.4 ( o nome fica por sua conta )

    rhc app create wordpress php-5.4 --from-code=https://github.com/getupcloud/wordpress-sqlite

Pronto, basta acessar a url e finalizar a instalação:

    http://wordpress-$yournamespace.getup.io

Você precisará inserir o usuário e senha de administração e também dar um nome para seu site Wordpress 
na primeira vez que acessar a url

Nota: Ao instalar plugins e temas, eles serão armazenados no diretório (data) do seu gear, $OPENSHIFT_DATA_DIR.
Você também pode baixar os temas e plugins diretamente no repositório git e fazer o deploy. Basta copiar os arquivos
nos diretórios php/wp-content/plugins e php/wp-content/themes.

Notas
=====

GIT_ROOT/.openshift/action_hooks/deploy:
	Este script é executado em todo 'git push'. Sinta-se à vontade para modificá-lo. Por padrão este script 
	cria os links para o diretório uploads e blogs.dir.


Segurança
-----------------------
Verifique a documentação do Wodpress para melhores práticas de segurança. O OpenShift gera automaticamente as chaves
de secretas no wp-config.php.
