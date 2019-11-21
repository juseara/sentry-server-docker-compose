# Configuração docker para servidor sentry ##

### Contexto
Esse repositorio tem como objetivo deixar um exemplo facil para criação e configuração de um servidor 
simples da plataforma sentry.

# Instalação ##
 

Você deve seguir os passos listado abaixa para instalar todas as dependências e iniciar o projeto.

1. Git clone desse repositorio
2. Crie um arquivo `sentry.env` apartir do arquivo `sample.sentry.env`
3. Gere uma nova `SENTRY_SECRET_KEY` pode usar o comando `sed -i "$ s/$/$(docker-compose run --rm sentry-base sentry config generate-secret-key)/" sentry.env`
4. Execute o comando `docker-compose run --rm sentry-base sentry upgrade --noinput` para atualizar a imagem do sentry
5. Em seguida execute o comando para iniciar o servidor `docker-compose up -d`
6. Crie um novo usuário admin para gerenciar seu servidor `docker-compose exec sentry-base sentry createuser --email YOUR_EMAIL --password YOUR_NEW_PASSWORD --superuser --no-input`
7. Sentry está disponivel localmente na porta: `880`
