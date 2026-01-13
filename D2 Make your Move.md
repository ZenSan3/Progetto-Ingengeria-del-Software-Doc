
## Dipartimento di Ingegneria e Scienza dell’Informazione

| **Progetto:**             | **Make your Move** |
| ------------------------- | ------------------ |
| **Titolo del documento:** | **Sviluppo**       |
 
**Document Info**

| Doc. Name       | D2-Sviluppo                        |
| :-------------- | :--------------------------------- |
| **Description** | Documento di sviluppo del progetto |
| **Doc. Number** | D2 V0.5                            |

## Indice
1. Web API's
2. Implementation details
3. Repository Organization
4. Branching strategy e organizzazione del lavoro
5. Dependencies
6. Database
7. testing
8. FrontEnd
9. Deployment

## 1. Web API's
Le API sono state documentate secondo le specifiche OpenApi v3 e la documentazione è disponibile su swagger al seguente indirizzo: https://app.swaggerhub.com/apis/yes-b83/MakeYourMoveOAS3/1.0
Riguardo il design delle API, alcune operazioni CRUD specificate (POST e DELETE di /stations per esempio) sono designate solo per ruoli alti come operatori e admin.

La specifica delle API è disponibile sulla repository del progetto (v. link in "Repository organization"). Nello specifico si tratta del file "oas3.yaml". Il suo contenuto è comunque riportato per intero sotto:

`openapi: 3.0.4`
`info:`
  `version: '1.0'`
  `title: "MakeYourMove OpenAPI 3.0"`
  `description: API per la gestione delle prenotazioni delle fermate`
  `license:`
    `name: MIT`
`servers:`
  - `url: http://localhost:8080/api/v1`
    `description: Localhost`
  - `url: https://make-your-move.onrender.com/api/v1`
    `description: render.com`
`paths:`
  `/auth:`
    `post:`
      `summary: Authenticate a user`
      `description: >-`
        `Authenticate a user and returns a JWT 'token'.`
      `responses:`
        `'200':`
          `description: 'Token created'`
          `content:`
            `application/json:`
              `schema:`
                `type: object`
                `properties:`
                  `success:`
                    `type: boolean`
                    `description: 'True if auth is successful'`
                  `token:`
                    `type: string`
                    `description: 'JWT token'`
        `'401':`
          `description: 'Unauthorised. Invalid credentials'`
      `requestBody:`
        `description: >-`
          `Email and password are required into the body.`
        `required: true`
        `content:`
          `application/json:`
            `schema:`
              `type: object`
              `required:`
                `- email`
                `- pwd`
              `properties:`
                `email:`
                  `type: string`
                  `description: 'Email address of the user'`
                `pwd:`
                  `type: string`
                  `description: 'Password of the user'`
            `examples:`
              `example1:`
                `value:`
                  `email: 'mario.rossi@unitn.it'`
                  `password: 'password'`
  `/users:`
    `get:`
      `description: >-`
        `View all the users`
        `It is possible to show users by their role /users?role={role}`
      `summary: View all users`
      `parameters:`
        `- in: query`
          `name: role`
          `schema:`
            `type: string`
            `enum: [default, operator, admin]`
      `responses:`
        `'200':`
          `description: 'Collection of users'`
          `content:`
            `application/json:`
              `schema:`
                `type: array`
                `items:`
                  `$ref: '#/components/schemas/User'`
    `post:`
      `description: >-`
        `Creates a new user in the system.`
      `summary: Register a new user`
      `requestBody:`
        `content:`
          `application/json:`
            `schema:`
              `$ref: '#/components/schemas/User'`
            `examples:`
              `example1:`
                `value:`
                  `username: 'Mario Rossi'`
                  `email: 'mario.rossi@unitn.it'`
                  `pwd: '123'`
                  `role: 'default'`
                  `disability: false`
      `responses:`
        `'201':`
          `description: 'User created. Link in the Location header'`
          `headers:`
            `'Location':`
              `schema:`
                `type: string`
              `description: Link to the newly created user.`
  `/stations:`
    `get:`
      `description: >-`
        `Gets the list of the available stations.`
      `summary: View all the stations`
      `responses:`
        `'200':`
          `description: 'Collection of stations'`
          `content:`
            `application/json:`
              `schema:`
                `type: array`
                `items:`
                  `$ref: '#/components/schemas/Station'`
    `post:`
      `description: Creates a new station in the system.`
      `summary: Add a new station`
      `requestBody:`
        `content:`
          `application/json:`
            `schema:`
              `$ref: '#/components/schemas/Station'`
            `examples:`
              `example1:`
                `value:`
                  `name: 'Piazza Dante'`
                  `address: 'Piazza Dante'`
                  `city: 'Trento'`
                  `CAP: 38122`
      `responses:`
        `'201':`
          `description: 'Station created. Link in the Location header'`
          `headers:`
            `'Location':`
              `schema:`
                `type: string`
              `description: Link to the newly created station.`
  `/stations/{stationId}:`
    `get:`
      `description: >-`
        `Gets the station with the given ID.`
      `summary: View a station`
      `parameters:`
        `- in: path`
          `name: stationId`
          `required: true`
          `schema:`
            `type: string`
          `description: 'ID of the station'`
      `responses:`
        `'200':`
          `description: 'Station found'`
          `content:`
            `application/json:`
              `schema:`
                `$ref: '#/components/schemas/Station'`
        `'404':`
          `description: 'Station not found'`
    `delete:`
      `description: >-`
        `Deletes the station with the given ID.`
      `summary: Delete a station`
      `parameters:`
        `- in: path`
          `name: stationId`
          `required: true`
          `schema:`
            `type: string`
          `description: 'ID of the station'`
      `responses:`
        `'204':`
          `description: 'Station deleted'`
        `'404':`
          `description: 'Station not found'`
  `/routes:`
    `get:`
      `description: >-`
        `Gets the list of the routes expressed by users.`
        `It is possible to show routes by userId /booklendings?userId={user}`
      `summary: View all routes`
      `security:`
        `- TokenQueryAuth: []`
          `XAccessTokenHeaderAuth: []`
      `parameters:`
        `- in: query`
          `name: userId`
          `schema:`
            `type: string`
            `description: 'ID of the user'`
      `responses:`
        `'200':`
          `description: 'Collection of routes'`
          `content:`
            `application/json:`
              `schema:`
                `type: array`
                `items:`
                  `$ref: '#/components/schemas/Route'`
    `post:`
      `summary: Create a route request`
      `description: >-`
        `Creates a new route request.`
        `Token must be passed in the header.`
        `The user and station must already exist in the system.`
        `The route request will be created with the next available date, but with the hour specified by the user.`
      `security:`
        `- TokenQueryAuth: []`
          `XAccessTokenHeaderAuth: []`
      `responses:`
        `'201':`
          `description: 'Route request created. Link in the Location header'`
          `headers:`
            `'Location':`
              `schema:`
                `type: string`
                `description: Link to the newly created route request.`
      `requestBody:`
        `description: >-`
          `The route object to be created.`
          `The user and station must already exist in the system.`
          `The route request will be created with the next available date, but with the hour specified by the user.`
        `required: true`
        `content:`
          `application/json:`
            `schema:`
              `$ref: '#/components/schemas/Route'`
            `examples:`
              `example1:`
                `value:`
                  `user: 'http://localhost:8080/api/v1/users/1'`
                  `stationA: 'http://localhost:8080/api/v1/stations/1'`
                  `stationB: 'http://localhost:8080/api/v1/stations/2'`
                  `DateOfArrival: 2026-01-01 09:00:00`
                  `DateOfCreation: 2025-12-31 12:56:31`
`components:`
  `securitySchemes:`
    `XAccessTokenHeaderAuth: # arbitrary name for the security scheme`
      `description: >-`
        `The API authentication.`
        `The API key must be passed in the header 'x-access-token'.`
        `The API key must be a valid JWT token.`
      `type: apiKey`
      `in: header`
      `name: x-access-token`
    `TokenQueryAuth: # arbitrary name for the security scheme`
      `description: >-`
        `The API authentication.`
        `The API key must be passed in the query string 'token'.`
        `The API key must be a valid JWT token.`
      `type: apiKey`
      `in: query`
      `name: token`
  `schemas:`
    `User:`
      `type: object`
      `required:`
        `- username`
        `- email`
        `- role`
        `- disability`
      `properties:`
        `self:`
          `type: string`
          `description: 'Link to the user'`
        `username:`
          `type: string`
          `description: 'Nickname of the user'`
        `email:`
          `type: string`
          `description: 'Email address of the user'`
        `role:`
          `type: string`
          `enum: [default, operator, admin]`
          `description: 'Type of the user. Default is the base level and Admin is the highest'`
        `disability:`
          `type: boolean`
          `description: 'Tells whether the user has requested some type of accessibility options or not'`
    `Station:`
      `type: object`
      `required:`
        `- name`
        `- address`
        `- city`
        `- CAP`
      `properties:`
        `self:`
          `type: string`
          `description: 'Link to the station'`
        `name:`
          `type: string`
          `description: 'Name of the station'`
        `address:`
          `type: string`
          `description: 'Address of the station'`
        `city:`
          `type: string`
          `description: 'City of the station'`
        `CAP:`
          `type: integer`
          `description: 'CAP of the station'`
    `Route:`
      `type: object`
      `required:`
      `- user`
      `- station`
      `properties:`
        `self:`
          `type: string`
          `description: 'Link to the route request'`
        `user:`
          `type: string`
          `description: 'Link to the user'`
        `station:`
          `type: string`
          `description: 'Link to the station'`
        `dateofarrival:`
          `type: string`
          `format: date-time`
          `description: 'Date specified by the user for the route request'`
        `dateofcreation:`
          `type: string`
          `format: date-time`
          `description: 'Date specified by the user for the route request'`
## 2. Implementation details
La webapp è stata sviluppata utilizzando NodeJS e Vue. Per la gestione dei dati abbiamo utilizzato MongoDB. Questo stack è stato motivato sia da conoscenze pregresse di alcuni membri del gruppo che dal materiale fornito e svolto durante il corso
## 2.1 Repository Organization
Il codice del progetto (https://github.com/ZenSan3/MakeYourMove) è disponibile su github ed è organizzato nel seguente modo:
- /src: cartella dei file sorgenti
	- /api: endpoint per le risorse di utenti e fermate
	- /middleware: middleware di autenticazione
	- /models: modelli dati mongoose
	- index.js: applicazione Express.js
- /frontend: codice per la parte del frontend
- /doc: cartella con la documentazione del codice
	- oas3.yaml: documentazione API
- package.json: file di configurazione del progetto npm
- .gitignore: file di configurazione repository git
- .env.example: esempio di file di configurazione variabili d’ambiente

Inoltre abbiamo una Repository per la documentazione dei deliverable (https://github.com/ZenSan3/Progetto-Ingengeria-del-Software-Doc), questa è stata fatta perché abbiamo usato Obsidian (Markdown) per scrivere la documentazione. Quindi abbiamo creato questa repo ed è strutturata come segue:
- /Class Diagram: cartella contenente il class diagram
- /Diagramma componenti: cartella contenente il diagramma dei componenti
- /Mockup-frontend: cartella con i mockup del frontend per D1 e D2
- /Slide Pitch Comune: cartella con le slide usate per la presentazione con il comune
- /Use Case Diagram: cartella con gli use case diagram
- /User Flow Diagram: cartella con lo user flow
- D1 Make Your Move: deliverable 1 del progetto (idea di progetto)
- D2 Make Your Move: deliverable 2 del progetto (sviluppo del progetto)
- D3 Make Your Move: deliverable 3 del progetto (design del progetto)
- D4 Make Your Move: deliverable 4 del progetto (resoconto finale)
## 2.2 Branching strategy e organizzazione del lavoro
In quanto Cristian Zeni è il developer del gruppo, la maggior parte dello sviluppo dell'applicazione è stata affidata a lui. Ciononostante, siccome il carico di lavoro era troppo per una sola persona, Alisia Wegher ha contribuito per alleggerire il carico.
Al momento della stesura di questa sezione del D2, sono stati eseguiti in totale 131 commit (considerando entrambe le repository), di cui 83 di Alisia Wegher, 46 di Cristian Zeni e 2 di Brando Giuffrida. Il numero così elevato di commit e lo sbilanciamento è giustificato dai seguenti fatti:
- Il numero descrive tutti i commit effettuati per il progetto. Si sta parlando quindi di entrambe le repository
- In questo momento la scrittura dei deliverable è quasi giunta al termine, mentre lo sviluppo dell'app è ancora attivo. Si prevede quindi un aumento del numero di commit da parte di Cristian Zeni
Eventuali altre criticità sono state descritte nell'apposita sezione del D4.
Inoltre su GitHub abbiamo utilizzato i nostri account personali per una questione di maggiore comodità. I nomi degli account appartengono alle seguenti persone:
- Aliport04: Alisia Wegher
- ZenSan3: Cristian Zeni
- BrandoDev: Brando Giuffrida

Per quanto riguarda la branching strategy, abbiamo preferito mantenere solo un branch oltre al "main" ("develop") per la realizzazione delle varie funzionalità perchè ulteriori "diramazioni" non le abbiamo ritenute necessarie per pulizia e organizzazione del codice.
Sulla repo dei deliverable invece, non è stata adottata alcuna branching strategy sempre per lo stesso motivo 
## 2.3 Dependencies
Il progetto npm si basa sui seguenti moduli esterni:
- Cors: Per il supporto alle chiamate cors
- Express: Framework web per il backend
- Google-auth-library: Supporto al login google
- Jsonwebtoken: Autenticazione JWT
- Mongoose: Libreria per interfacciarsi con mongoDB
E le seguenti dipendenze di sviluppo:
- Dotenv: Gestione variabili d’ambiente in ambiente dev da file.env
- Jest: Testing
- Supertest: Testing endpoint express
