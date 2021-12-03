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

## Arquivos de configuração

### application.properties
````

spring.profiles.active=${APP_PROFILE:prod}

spring.jpa.open-in-view=false

security.oauth2.client.client-id=${CLIENT_ID:dscatalog}
security.oauth2.client.client-secret=${CLIENT_SECRET:dscatalog123}

jwt.secret=${JWT_SECRET:MY-JWT-SECRET}
jwt.duration=${JWT_DURATION:86400}
`````

### application-prod.properties
````
spring.datasource.url=${DB_URL}
spring.datasource.username=${DB_USERNAME}
spring.datasource.password=${DB_PASSWORD}

spring.jpa.database-platform=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.properties.hibernate.jdbc.lob.non_contextual_creation=true
spring.jpa.hibernate.ddl-auto=none
`````













