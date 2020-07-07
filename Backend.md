# BackEnd com Node.js

## O que é JWT?
JSON Web Token - um padrão que define como transmitir e armazenar objetos JSON de forma compacta e segura entre diferentes aplicações. 
Os dados podem ser validados a qualquer momento, pois o token é validado digitalmente. 

Três seções:
    * Header
    * Payload 
    * Signatura

### Header
Objeto JSON que define informações sobre o token, qual seu tipo, qual criptografia foi usada na assinatura do token, etc. 

### Payload
Objeto JSON com as informações da entidade tratada (exemplo: o usuário audenticado, nome do usuário ou id, etc).
Pode ser de 3 tipos: reserved claims (atributos não obrigatórios, mas recomendados), public claims (atributos usados pelas aplicações, como name, roles do usuário, etc.) e private claims (atributos para compartilhar informações entre aplicações). 
São usados na validação do token. 
Por segurança recomenda-se não armazenar informações confidenciais ou sensívels no Token, apenas essenciais para a aplicação identificar o usuário.

### Signatura
Concatenação dos hashes gerados pelo Header e Payload. 

## Como o token é usado?

Usuário faz login em um serviço de autenticação => Token JWT é criado e retorna para o client

O token é enviado para as APIS pelo header authorization de cada requisição HTTP com a flag Bearer

Com o Token a API não precisa consultar as informações do usuário no banco de dados a cada requisição.

