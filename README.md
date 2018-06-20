## About this
This is to help Maniaplanet coders to setup a working OAuth2 client to communicate with the **Maniaplanet v4** webservices by using **Symfony 4.1**. Yet, it is simply a fresh symfony install with "login with maniaplanet" functionality and a few sample sites.

## Getting started
Things you should have some basic knowledge about:
 - Composer. We assume you have installed it globally
 - Symfony. Learning by doing is possible, though it's a good idea to at least read through their "Getting Started" section in the docs
 - Basics of OAuth2

### Get the Symfony skeleton using composer:

    composer -vv create-project symfony/website-skeleton mp-oauth 4.1.0
I recommend starting with the version we have written the sample on and then upgrade step by step. That makes it easier to fix errors occuring in newer versions.



## Description of files
These files are relevant and need to be created/updated.
### Mandatory files
- src/Entity/ManiaplanetUser.php: object representing the user (containing login, nickname ...)
- src/Repository/ManiaplanetUserRepository.php: dummy respository created alongside the ManiaplanetUser entity by bin/console make:entity
- src/Security/OAuth2/*: contains the basic functionality of the client

### App files
List of files which are used to demonstrate the client
- src/Controller/*: simple page controllers
- src/Controller/ManiaplanetController.php: is special because it is the start and endpoint of the authentication process
- templates/*

### Config files
List of configs I have edited in order to get the app running
- config/packages/knpu_oauth_client.yaml
- config/packages/security.yaml
- config/routes.yaml
- config/services.yaml: adding a service tag for the provider (last line)
- .env: create this file from .env.dist. Insert DB connection and OAuth credentials

