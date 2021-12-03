# Heroku-Deploy

## CI/CD padrão do Heroku
### 1. Criar projeto no Heroku, provisionar Postgres e instanciar base de dados

### 2. Associar o projeto local ao Github e ao Heroku
 - heroku -v
- heroku login
- heroku git:remote -a nome-do-app
- git remote -v

### 3. Arquivo system.properties
- java.runtime.version=11

### 4. Configurar variáveis de ambiente no Heroku
- APP_PROFILE

- CLIENT_ID
- CLIENT_SECRET
- JWT_SECRET
- JWT_DURATION

- DB_URL
- DB_USERNAME
- DB_PASSWORD

### 5. Realizar deploy

#### Repositório comum:
- git push heroku main

#### Monorepositório (subpasta):
- git subtree push --prefix backend heroku main











