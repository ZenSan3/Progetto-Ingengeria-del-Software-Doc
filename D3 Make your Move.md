
## Dipartimento di Ingegneria e Scienza dell’Informazione

| **Progetto:**             | **Make your Move**          |
| ------------------------- | --------------------------- |
| **Titolo del documento:** | **Analisi e Progettazione** |
 
**Document Info**

| Doc. Name       | D3-AnalisiProgettazione          |
| :-------------- | :------------------------------- |
| **Description** | Documento di design del progetto |
| **Doc. Number** | D3 V0.1                          |

## Indice

1. Analisi dei componenti
2. Diagramma delle Classi
	1. Diagramma delle classi complessivo
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
##### IR - Mail utente
Il componente necessita della mail dell’utente per poter inviare le varie notifiche.
##### IR - Avvenuto cambio password
Si "attiva" in caso di avvenuta modifica della password da parte dell’utente. Dialoga inoltre con la componente “Gestione impostazioni”, da cui prende questa informazione
##### IF - Contenuto mail
Rappresenta il contenuto delle mail (oggetto, testo e indirizzo email di destinazione) che verranno inviate tramite questo componente
#### CMP4: Gestione nuova registrazione
##### Descrizione:
Questo componente si occupa di richiedere all’utente i propri dati per effettuare una nuova registrazione. L’utente fornirà i propri dati personali, la propria mail e la password, che verranno salvati all’interno del database.
##### IR - Dati personali utente
I dati dell'utente comprendono mail di registrazione, username, tipo di utente e se è portatore di disabilità
##### IR - Richiesta registrazione
Richiede all’utente o al personale, a seconda di chi sta utilizzando il sistema, le proprie credenziali d’accesso e ne verifica la correttezza dialogando con il database.
##### IF - Mail utente
Il componente necessita della mail dell’utente per poter inviare alla stessa le varie notifiche
##### IF - Account utente
Il componente deve avere accesso ai dati presenti nell’account dell’utente così da poterli salvare e fornire i dati qualora fosse necessario

### Diagramma dei Componenti
![[DiagrammaComponenti.drawio.svg]]

