
## Dipartimento di Ingegneria e Scienza dell’Informazione

| **Progetto:**             | **Make your Move**          |
| ------------------------- | --------------------------- |
| **Titolo del documento:** | **Analisi e Progettazione** |
 
**Document Info**

| Doc. Name       | D3-AnalisiProgettazione          |
| :-------------- | :------------------------------- |
| **Description** | Documento di design del progetto |
| **Doc. Number** | D3 V1.0                          |

## Indice

1. Analisi dei componenti
2. Diagramma delle Classi
3. Dal class diagram alle API
4. Business Plan
## 1. Analisi dei componenti
In questo capitolo verrà presentata l’architettura in termini di componenti (CMP) interni al sistema definiti sulla base dei requisiti analizzati in precedenza. Successivamente verranno mostrati tramite un diagramma dei componenti per rappresentare le loro interconnessioni, identificando quindi le interfacce tra questi e verso sistemi esterni.
### Definizione dei componenti
Legenda: 
- CMP: Componente
- IR: Interfaccia richiesta
- IF: Interfaccia fornita
#### CMP1: Gestione autenticazione
##### Descrizione:
Si occupa della funzionalità di registrazione di un account e accesso tramite delle credenziali. Include una pagina per il login e il logout e permette di identificare coloro che effettuano l’accesso al sistema, permettendogli di accedere alle funzionalità a loro riservate. L’utente può selezionare una modalità di accesso alternativa, ovvero l'utilizzo delle proprie credenziali già in possesso su Google.
##### IR - Credenziali di accesso
Le credenziali includono e-mail e password. Sono richieste all’utente per l’accesso al sistema
##### IR - Autorizzazione autenticazione da Google
Il componente, per chi sceglie questa modalità di accesso, deve richiedere l'accesso al sistema al Google Auth Service che, previo controllo, conferma che queste siano corrette
##### IR - Dati utente
I dati dell'utente comprendono mail di registrazione, username, tipo di utente e se è portatore di disabilità
##### IF - Richiesta autenticazione verso Google
Indirizzamento dell’utente verso Google Auth Service per l’inserimento delle credenziali Google
##### IF - Data autenticazione
La data e l’ora dell’autenticazione dell’utente vengono salvate all’interno del database. In questo modo verranno salvati i dati del log
##### IF - Autenticazione
Questa interfaccia permette all'utente che ha già effettuato l'accesso di accedere all'applicazione, in modo da poter usufruire dei servizi e delle funzioni della stessa
##### IF - Richiesta registrazione
L’utente richiede di effettuare la registrazione al portale fornendo i propri dati (username, tipo di utente, disabilità, email) i quali vengono salvati nel database.
#### CMP2: Gestione impostazioni
##### Descrizione:
Il componente si occupa di raggruppare le varie impostazioni dell’applicazione come il cambio della lingua usata nell’applicazione, della password, delle preferenze dei veicoli,... Permette inoltre all’utente di modificare i propri dati personali. Se l’utente effettua per la prima volta il login, viene obbligato ad effettuare un cambio password
##### IR - Modifica dei dati
Richiede i nuovi dati da sostituire a quelli precedentemente registrati nel sistema
##### IR - Autenticazione
Questa interfaccia permette all'utente che ha già effettuato l'accesso di accedere all'applicazione, in modo da poter usufruire dei servizi e delle funzioni della stessa. In questo caso, l'autenticazione è necessaria per poter gestire il proprio profilo utente
##### IF - Avvenuto cambio password
Si "attiva" in caso di avvenuta modifica della password da parte dell’utente. Dialoga inoltre con la componente “Gestione invio mail” notificandola di questo cambiamento
##### IF - Dati modificati
Raggruppa le varie modifiche apportate dall’utente attraverso le impostazioni e sostituisce i dati presenti con i dati modificati da quest’ultimo
#### CMP3: Gestione invio mail
##### Descrizione:
Il componente si occupa di richiedere l’invio di una e-mail all’indirizzo di posta elettronica dell’utente per informarlo sul percorso della linea dinamica, l’avvenuta modifica della password o la creazione di un nuovo account (password temporanea inclusa). Il contenuto della mail viene elaborato dal componente e viene successivamente reso a disposizione del sistema esterno che invierà la mail.
##### IR - Email utente
Il componente necessita della mail dell’utente per poter inviare le varie notifiche.
##### IR - Avvenuto cambio password
Si "attiva" in caso di avvenuta modifica della password da parte dell’utente. Dialoga inoltre con la componente “Gestione impostazioni”, da cui prende questa informazione
##### IR - Tratta effettiva
Quando la linea dinamica viene creata, il componente "Gestione richiesta tratta" dialoga con questo e manda una mail all'utente con tutte le informazioni rilevanti a ciò (passando per "contenuto mail")
##### IR - Conferma richiesta
Quando l'utente invia una richiesta di tratta, il componente (passando per "contenuto mail") invierà a quest'ultimo una mail confermando il corretto invio e la ricezione della richiesta a chi di competenza 
##### IF - Contenuto mail
Rappresenta il contenuto delle mail (oggetto, testo e indirizzo email di destinazione) che verranno inviate tramite questo componente
#### CMP4: Gestione nuova registrazione
##### Descrizione:
Questo componente si occupa di richiedere all’utente i propri dati per effettuare una nuova registrazione. L’utente fornirà i propri dati personali, che verranno salvati all’interno del database.
##### IR - Dati personali
I dati dell'utente comprendono mail di registrazione, username, tipo di utente e se è portatore di disabilità
##### IR - Richiesta registrazione
Richiede all’utente o al personale, a seconda di chi sta utilizzando il sistema, le proprie credenziali d’accesso e ne verifica la correttezza dialogando con il database.
##### IR - Password crittografata
Richiede all’utente la propria password e verrà crittografata tramite un servizio esterno, in modo da non salvarla in chiaro
##### IF - Email utente
Il componente fornisce la mail dell’utente, in modo che "Gestione invio mail" possa inviare le varie notifiche
##### IF - Account utente
Il componente fornisce l'accesso ai dati presenti nell’account dell’utente così da poterli salvare e fornire qualora fosse necessario
#### CMP5: Visualizzazione mappa
##### Descrizione:
Questo componente si occupa di far visualizzare la mappa della città all'utente. Inoltre questo potrà interagirci in modo da poter navigare più agevolmente sul territorio
##### IR - Autenticazione
Questa interfaccia permette all'utente che ha già effettuato l'accesso di accedere all'applicazione, in modo da poter usufruire dei servizi e delle funzioni della stessa. In questo caso, l'autenticazione è necessaria per poter visualizzare la mappa interattiva
##### IR - Indirizzi stazioni e fermate
Il componente richiede ad un servizio esterno gli indirizzi delle stazioni e delle fermate
##### IR - Mappa stazioni e fermate
Il componente richiede ad un servizio esterno la mappa (o posizione geografica) delle stazioni e delle fermate
##### IF - Invio richiesta mappa stazioni
Il componente fornisce le informazioni inserite dall'utente riguardo una particolare stazione o fermata
#### CMP6: Sistema ricerca stazioni
##### Descrizione:
Questo componente si occupa di far visualizzare la mappa della città all'utente. Inoltre questo potrà interagirci in modo da poter navigare più agevolmente sul territorio
##### IR - Autenticazione
Questa interfaccia permette all'utente che ha già effettuato l'accesso di accedere all'applicazione, in modo da poter usufruire dei servizi e delle funzioni della stessa. In questo caso, l'autenticazione è necessaria per poter effettuare ricerche
##### IR - Parametri di ricerca
Il componente richiede dei parametri all'utente per poter effettuare una ricerca sulle stazioni o sulle fermate
#### CMP7: Gestione richiesta tratta
##### Descrizione:
Questo componente si occupa di gestire le richieste per la linea dinamica effettuate dagli utenti
##### IR - Autenticazione
Questa interfaccia permette all'utente che ha già effettuato l'accesso di accedere all'applicazione, in modo da poter usufruire dei servizi e delle funzioni della stessa. In questo caso, l'autenticazione è necessaria per poter effettuare richieste per la linea dinamica
##### IR - Lista richieste
Il componente richiede dal database la lista delle richieste effettuate in giornata, in modo che un operatore o admin possa processarle
##### IR - Codice utente
Il componente richiede il codice utente (ovvero lo username) in modo da poter identificare univocamente le richieste
##### IR - Orario partenza
Il componente richiede l'orario di partenza desiderato dell'utente, che rientra tra le informazioni obbligatorie per la compilazione della richiesta
##### IR - Nome partenza
Il componente richiede il nome della stazione o fermata di partenza desiderata dell'utente, che rientra tra le informazioni obbligatorie per la compilazione della richiesta
##### IR - Nome arrivo
Il componente richiede il nome della stazione o fermata di arrivo desiderata dell'utente, che rientra tra le informazioni obbligatorie per la compilazione della richiesta
##### IF - Invio richiesta
Il componente fornisce la richiesta compilata dall'utente da "conservare" nel database
##### IF - Tratta effettiva
Una volta processate le richieste, viene creata la linea dinamica. Questo componente dialoga con "Gestione invio mail" in modo da notificare tutti gli utenti
##### IF - Conferma richiesta
Se la richiesta va a buon fine (ovvero è stata compilata ed è stato cliccato su conferma), all'utente arriverà una mail che conferma ciò
#### CMP8: Gestione Database
##### Descrizione:
Il componente funge da raccolta dati. Salva nel database le attività del personale e dell’utente e tutti i dati relativi ad essi con le relative modifiche, quando presenti. Si interfaccia inoltre con la componente gestione trend inviando i dati relativi alle tratte degli utenti
##### IR - Dati database
Raccolta di tutti i dati presenti all’interno del database sia riguardanti gli operatori/admin sia l’utente
##### IR - Dati modificati
Raggruppa le varie modifiche apportate dall’utente attraverso le impostazioni e sostituisce i dati presenti con i dati modificati
##### IR - Account utente
Il componente deve avere accesso ai dati presenti nell'account dell'utente così da poterli salvare e fornire quando necessario.
##### IR - Data autenticazione
La data e l'ora dell’autenticazione dell’utente vengono salvate all'interno del database. In questo modo verranno salvati i dati del log
##### IR - Invio richiesta
Il componente richiede la richiesta compilata dall'utente, in modo da poterla "conservare" nel database
##### IF - Dati utente
I dati dell'utente comprendono mail di registrazione, username, tipo di utente e se è portatore di disabilità
##### IF - Attività personale e utenza
Raccolta delle varie attività compiute dal personale e dall’utente all’interno del sistema
##### IF - Modifiche database
Funzione che garantisce al sistema di salvare qualunque modifica apportata ai dati personali
##### IF - Dati tratte
Raccolta delle informazioni relative alle tratte effettuate e richieste dagli utenti (es: orario della partenza, luogo di partenza e arrivo)
##### IF - Lista richieste
Funzione che fornisce la lista delle richieste da far processare ad admin e operatori
#### CMP9: Gestione trend
##### Descrizione:
Questo componente si occupa di gestire e far visualizzare ad operatori e admin i dati relativi alle linee dinamiche
##### IR - Dati tratte
Raccolta delle informazioni relative alle tratte effettuate dalla linea dinamica
##### IR - Analisi dati tratte
Il componente richiede dei parametri per poter gestire e far visualizzare i dati come l'operatore/admin desidera
##### IF - Dati tratte richieste
Raccolta delle informazioni relative alle richieste degli utenti
### Diagramma dei Componenti
![[DiagrammaComponenti.drawio.svg]]
## 2. Diagramma delle classi
In questa sezione vengono presentate le classi previste all'interno del progetto Make Your Move. 
Le classi sono state individuate tramite l'analisi degli use case diagram e del diagramma dei componenti.
### Definizione classi
#### 1. Utente
Abbiamo individuato l’attore “Utente”, da cui la classe omonima, che è colui che dopo aver effettuato il login all'interno della webapp può accedere a tutte le informazioni che riguardano sé e lo stato di eventuali prenotazioni fatte. Dentro questa classe sono state inserite le operazioni di gestione delle impostazioni personali.
#### 2. Operatore
L'operatore è lo staff che gestisce le richieste effettuate dagli utenti e può visualizzare le statistiche per rilevare le zone più frequentate
#### 3. Admin
L'admin è colui che gestisce gli utenti e le fermate, in aggiunta a ciò che esegue l'operatore
#### 4. Gestione nuova registrazione e autenticazione
L'utente può registrarsi o fare login tramite un'apposita pagine del sistema. Una volta registrato, all'utente verrà assegnato un codice identificativo e potrà accedere alle funzionalità dell'app
#### 5. Gestione richiesta tratta
Per la gestione delle richieste è stata identificata la classe "richiesta tratta" per gestire le informazioni e le operazioni quando un utente effettua una richiesta. L’operatore o admin registra il noleggio all’interno del sistema salvando il codice identificativo dell’utente, l'ora della partenza e i luoghi di partenza e arrivo.
#### 6. Gestione trend
Per la gestione del trend è stata identificata la classe trend che servirà a gestire le informazioni riguardo ai trend riguardante le fermate e le tratte più quotate dagli utenti
#### 7. Sistema ricerca fermate
Quando si vuole fare una ricerca delle stazioni da inserire come partenza e destinazione, la classe "Lista fermate" andrà ad attingere da "Fermate", ottenendo così un elenco di quelle pertinenti ai parametri di ricerca inseriti
#### 8. Gestione invio mail
Il componente “Gestione invio mail” è rappresentato dalla classe mail che invia una mail all’utente (all’indirizzo fornito durante la registrazione) per informarlo riguardo la creazione della tratta per il giorno successivo, l'avvenuto cambio password,...
#### 9. Visualizzazione mappa
Con questa classe (Mappa fermate) si potrà avere accesso alle informazioni delle fermate (ubicazione, disponibilità,...)
#### 10. Attività
Questa classe rappresenta il salvataggio delle azioni svolte da utenti, operatori e admin. Le attività salvate riguardano login, richiesta tratte e le modifiche ai dati degli utenti. Di ogni attività verrà salvato l'ID della persona, la data e l’orario in cui è stata effettuata l’attività. Tutte queste informazioni verranno poi salvate nel database.
### Diagramma delle classi
![[Diagramma delle classi.drawio.svg]]
## 3. Dal class diagram alle API
Di seguito si vede una tabella con la mappatura tra i metodi presenti nel diagramma delle classi e le API:

N.B: ciò che non si trova nella tabella sottostante implica che quei metodi non sono gestiti tramite API

| Classe          | Metodo                   | HTTP OP | URL + Query params | Body Request                                    | Response       | Note                                                                     |
| --------------- | ------------------------ | ------- | ------------------ | ----------------------------------------------- | -------------- | ------------------------------------------------------------------------ |
| Utente          | cambiaPassword(password) | PUT     | /api/users/ID      | {password}                                      | 200<br>User    |                                                                          |
| Utente          | cambia...()              | PUT     | /api/users/ID      | ...                                             | 200<br>User    |                                                                          |
| Utente          | effettuaAccesso()        | PUT     | /api/auth          | {username, password}                            | 200<br>{token} | è possibile fornire username e password per ottenere un token di accesso |
| Utente          | cercaFermate()           | GET     | /api/stations/ID   | -                                               | 200<br>Station |                                                                          |
| Utente          | visualizzaMappa()        | GET     | /api/users/ID      | -                                               | 200<br>User    | implementata solo nel frontend usando l'indirizzo Users                  |
| Utente          | visualizzaPrenotazioni() | GET     | /api/Routes/ID     | -                                               | 200<br>Routes  |                                                                          |
| Admin           | gestioneUtenti()         | DELETE  | /api/Users/ID      | -                                               | 204            |                                                                          |
| RichiestaTratta | creaTratta()             | POST    | /api/Routes/ID     | {username, stationA, stationB, dateOfDeparture} | 201<br>Routes  |                                                                          |
| Fermata         | mostraDettagli()         | GET     | /api/stations/ID   | -                                               | 200<br>Station |                                                                          |

## 4. Business Plan
Abbiamo stilato un business plan per Make Your Move. Vista la natura dell'applicazione, quindi a servizio dei cittadini, abbiamo deciso di renderla fruibile gratuitamente. Gli introiti dell'applicazione verranno generati da una partnership con gli erogatori dei servizi (inizialmente con Trentino Trasporti).
Le specifiche potranno essere viste al seguente link (documento del prospetto economico): https://docs.google.com/spreadsheets/d/1vl38HC6hu52xKXNOjyRckl_DpkZUGGk7QQY_Uxu61nE/edit?usp=sharing