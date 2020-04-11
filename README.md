# Configurações do framework fuelPHP

## Download
https://fuelphp.com/

Descompactar na pasta do projeto

Ou

## Instalar o oil:
curl -L https://get.fuelphp.com/oil | sh

Com o comando acima agora temos no path o comando oil que executa uma grande quantidade de comandos para o fuelPHP, mas ainda com recursos mais úteis como o scaffold e o admin.

## Criar projeto
oil create blog

ou

oil create apps/blog

cd apps/blog

## Podemos criar aplicativos também usando o composer:
https://fuelphp.com/docs/installation/instructions.html

## Se em linux ou similar
Rodar para configurar as permissões, logo após a criação de um projeto e ao tentar rodar pela web recebemos o erro:
Fuel\Core\FuelException [ Error ]:
Unable to create the log file.

oil refine install

## Atualizar as dependências
composer update

## Configurações

### Banco de dados
fuel/app/config/development/db.php

### Habilitando o ORM e Auth
app/config/config.php

E abaixo de

return array(

Adicionar

    'always_load' => array(
        'packages' => array(
            'orm', 'auth',
         ),
     ),

### Mudar para driver Ormauth

Copiar packages/auth/config/auth.php para app/config/

Deixar assim:

return array(
    'driver'                 => 'Ormauth',
    'verify_multiple_logins' => false,
    'salt'                   => '181818nsnsns3939393',
    'iterations'             => 10000,
);

### Configurar rotas

fuel/app/config/routes.php

Idealmente para

admin/login

Agora é uma boa hora para ver o tutorial sobre a criação de aplicativos com o fuelPHP.
