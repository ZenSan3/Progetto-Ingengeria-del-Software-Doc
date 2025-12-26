
## Dipartimento di Ingegneria e Scienza dell’Informazione

| **Progetto:**             | **Make your Move**          |
| ------------------------- | --------------------------- |
| **Titolo del documento:** | **Descrizione di Progetto** |
 
**Document Info**

| Doc. Name       | D1-DescrizioneProgetto                                                                                          |
| :-------------- | :-------------------------------------------------------------------------------------------------------------- |
| **Description** | Documento di analisi dei requisiti funzionali, non funzionali, user story, epiche, front-end design e user flow |
| **Doc. Number** | D1 V0.8                                                                                                         |

## Indice

1. Il progetto Make your Move
2. Requisiti Funzionali
3. Requisiti Non Funzionali
4. Use case Diagram
5. User Stories
6. Epiche
7. Front-end design
8. User Flow

## 1\. Il progetto Make your Move
### Problema

![[1_Problematiche.jpg]]
Il problema che abbiamo identificato riguarda una macro-categoria, ovvero traffico e viabilità. A Trento, per esempio, non è difficile trovare strade congestionate (specialmente in fasce orarie "di punta") a causa del traffico che talvolta diventa anche insostenibile, con pesanti ripercussioni sull'ambiente, e sui cittadini.
Effettuando interviste ad amici e parenti, abbiamo notato che, chi vorrebbe utilizzare mezzi di trasporto pubblici, spesso non si trova in una posizione da poter essere incentivato ad usarli. Infatti, il traffico eccessivo comporta un rallentamento del mezzo, accumulando ritardo di conseguenza. Specialmente per chi non si può permettere di arrivare a destinazione in ritardo o per chi deve effettuare dei cambi, si andrà a preferire il mezzo personale, causando così un circolo vizioso interminabile.
Abbiamo inoltre osservato che, per quanto riguarda gli autobus, la domanda non è sempre seguita dall'offerta. Il cittadino si trova di fronte a due problemi principali:
- Pochi autobus ma molto pieni. Questo non solo causa problemi di sicurezza a bordo del veicolo, ma suggerisce un problema organizzativo e porta i cittadini a scegliere soluzioni alternative, spesso più inquinanti.
- Molti autobus quasi vuoti. Queste risorse potrebbero essere ricollocate altrove, dove c'è un reale bisogno.
### Soluzione

![[2_Soluzione.jpg]]
Il progetto ha come obiettivo la realizzazione di un’applicazione web per aiutare i cittadini a spostarsi nel comune di Trento. Il core di Make Your Move consiste infatti nella creazione di tratte dinamiche per le linee autobus. La tratta viene calcolata subito prima dell'inizio del turno, in base alle segnalazioni raccolte dagli utenti, ovvero Il punto di partenza, quello di arrivo e i relativi orari. Arriverà poi una notifica all'utente su quale sarà il suo bus, dove e quando giungerà.
### Vantaggi

![[3_Vantaggi.jpg]]
I vantaggi che si otterranno con l'utilizzo della webapp sono molteplici.
Per il comune:
- Miglioramento della viabilità: la maggiore pianificazione degli itinerari dei cittadini consente un flusso del traffico sensibilmente più efficiente.
- Minor impatto ambientale: autobus e altre soluzioni di mobilità sostenibile, hanno un impatto significativamente minore sulle emissioni di co2.
- Costi minori: ottimizzando l'uso dei veicoli pubblici in base alle richieste degli utenti, i costi di mantenimento saranno più contenuti.

Per il cittadino:
- Meno disagi: con una gestione del traffico più controllata, la viabilità cittadina ottiene maggior resilienza, riducendo ritardi e congestioni dei viadotti.
- Accesso remoto: grazie all'interfaccia web accessibile da tutti i dispositivi, Make your Move è facilmente accessibile sempre e ovunque.
- Notifiche/promemoria: Make Your Move manda notifiche all'utente dell'itinerario creato per il giorno successivo, al fine di agevolare l'uso dell'app e garantire la più alta adesione possibile agli itinerari.

### Limiti dell'applicazione:
- Dipendenza da una connessione internet: La nostra webapp necessita di una connessione internet per poter usufruire delle funzionalità
- Accessibilità limitata per utenti non digitali: sebbene Make Your Move sia pensata per essere facile e veloce da usare, gli utenti con poca familiarità con gli smartphone potrebbero fare fatica ad utilizzare l'app al pieno delle potenzialità.
- Poche possibilità per gli utenti con disabilità: L'app non è usufruibile a pieno da utenti affetti da disabilità visive, rendendo quindi alcune possibilità/alternative non fattibili.
- Manutenzione e aggiornamenti: La webapp potrebbe non essere usufruibile per brevi periodi di tempo, in orari non di punta, per manutenzioni programmate o malfunzionamenti, che comunque non supereranno il quantitativo di tempo prestabilito (RNF4).
- Sicurezza e Privacy: sebbene l'applicazione sia pensata per rispettare norme di sicurezza e privacy nei confronti dell'utente, potrebbe non essere del tutto esente dal rischio di potenziali attacchi e violazioni informatiche, compromettendo di conseguenza i dati sensibili inseriti
- Integrazione con sistemi esistenti: la compatibilità e l'integrazione futura con sistemi esistenti potrebbe risultare difficoltosa con sistemi attualmente in uso 
- Dipendenza dall'infrastruttura tecnica: Le prestazioni dell'applicazioni dipendono dalla qualità e dalla capacità dei server. Di conseguenza, se l'hardware non soddisfa queste due proprietà, potrebbero presentarsi problemi sul servizio (N.B: RNF2 è stato scritto presupponendo che l'hardware sia adeguato per le richieste)
- Possibili costi iniziali per il comune e per Trentino Trasporti: l'implementazione del servizio può comportare un piccolo investimento iniziale riguardo la formazione del personale, l'investimento di nuove risorse e la possibile integrazione con sistemi già esistenti.
### Q&A:
- *Quale sarebbe la funzionalità principale dell'applicazione?*
- L'obbiettivo principale di Make Your Move consiste nella generazione dinamica di linee per autobus basate sulle richieste reali degli utenti. Percorso e orari vengono calcolati la sera prima, ottimizzando così tragitto, tempi di attesa e carico dei passeggeri
- *Non è confusionario il fatto che delle linee verranno modificate ogni giorno?*
- Make your Move non andrà a modificare tratte già preesistenti, ma verrà creata una linea apposita (nome in codice, "linea D") in modo da generare meno confusione possibile, specialmente tra i nostri utenti più abitudinari :)
- *Se mi dimentico di inserire la tratta per il giorno successivo come faccio ad arrivare a destinazione? Mi tocca per forza usare il mezzo personale?*
- Non necessariamente. Make your Move salva le tratte che l'utente ha considerato come "abitudinarie". In caso il percorso desiderato sia "straordinario" e/o l'utente si è dimenticato di inserirlo, l'applicazione propone (in base a disponibilità e preferenze) mezzi pubblici alternativi come linee autobus tradizionali, monopattini elettrici o biciclette. Il veicolo personale (inteso come auto o moto) resterà disponibile in extremis. 
- *Perchè nell'applicazione c'è la possibilità di selezionare più veicoli? Non generava tratte dinamiche per autobus?*
- Sì, Make Your Move è una webapp che genera linee dinamiche per gli autobus. La disponibilità di altri mezzi è stata pensata per fornire un ulteriore supporto alla mobilità in caso la "linea D" non passasse nei pressi dell'utente che ne ha fatto richiesta
- *Sono un utente con disabilità. L'applicazione può adattarsi alle mie esigenze?*
- Certamente! Make Your Move al momento della registrazione chiederà le preferenze dei veicoli che l'applicazione offre, in modo che sia utenti con bisogni speciali che persone che preferiscono evitare alcune opzioni, possano personalizzare i loro percorsi con serenità.

## 2. Requisiti Funzionali
### Requisiti funzionali comuni ad Admin, Operatore e Utente Base
- [x] RF1: Registrazione: Il sistema deve permettere agli utenti di registrarsi utilizzando mail e un nickname, garantendo così lo pseudo-anonimato (RNF5) e far in modo di tenere traccia di tratte e veicoli preferiti (RF7 e RF10)
- [x] RF2: Login: Il sistema deve permettere agli utenti di poter accedere col proprio account creato precedentemente (RF1) così da poter accedere ai propri dati salvati e per poter far riconoscere le richieste dei servizi al server
- [x] RF3: Ricerca: L'utente deve poter effettuare ricerche dei luoghi per indicare il punto di partenza e arrivo
- [x] RF4: Visualizzazione mappa: L'utente deve essere in grado di visualizzare e interagire con la mappa interattiva

### Requisiti funzionali Operatore
- [x] RF5: Richieste utenti: Il sistema deve garantire agli operatori di visualizzare in blocco le richieste di tratte effettuate dagli utenti (RF7) e di poterle accettare o rifiutarle
- [x] RF6: Statistiche: Il sistema deve poter permettere agli operatori di visualizzare le statistiche riguardanti le richieste e le persone effettivamente salite

### Requisiti funzionali Utente
- [x] RF7: Richiesta linea dinamica: Il sistema deve permettere all'utente di richiedere il punto di partenza e di arrivo, con i relativi orari
- [x] RF8: Ricevuta di approvazione: Il sistema, una volta che genera la tratta della linea dinamica, deve fornire una risposta all'utente, dichiarando dove e quando si troverà il bus
- [x] RF9: Proposta di alternativa: Il sistema, se la tratta è satura o la generazione di questa risulta troppo lontana dall'utente, deve fornire un'alternativa valida in base a disponibilità e preferenze (RF10)
- [x] RF10: Inserimento preferenze: Il sistema deve consentire all'utente di inserire i veicoli preferenziali
### Requisiti funzionali Admin
- [x] RF11: Modifiche: Il sistema deve permettere agli admin di poter fare modifiche all'app (esempio: disabilitare una fermata)
- [x] RF12: Gestione utenti: Il sistema deve permettere agli admin di gestire e dare permessi agli utenti

## 3. Requisiti Non Funzionali
- [x] RNF1: Compatibilità: Il sistema deve essere pienamente compatibile con i seguenti browser: Chrome/Chromium 105 o superiore e Safari 16.4 o superiore. Il software deve garantire un'esperienza utente coerente e funzionale su tutte le piattaforme supportate, assicurando la corretta visualizzazione delle interfacce e il pieno funzionamento di tutte le funzionalità, indipendentemente dal browser utilizzato.
- [ ] RNF2: Performance: Il sistema deve garantire tempi di risposta rapidi e prestazioni efficienti, in modo tale che ogni operazione, come il login, la registrazione o la prenotazione di una tratta, venga completata entro un massimo di 2 secondi per il 95% delle richieste. Questo requisito deve essere mantenuto anche durante i picchi di utilizzo, con un carico simultaneo di almeno 100 utenti connessi al sistema. Il sistema deve inoltre scalare facilmente per supportare un numero crescente di utenti senza compromettere le prestazioni.
- [ ] RNF3: Scalabilità: Il sistema deve essere progettato per garantire la scalabilità, consentendo la gestione efficiente di qualsiasi tipo di operazione fino a un massimo di 10.000 utenti simultanei. Il software dovrà mantenere prestazioni ottimali (RNF2) anche con un elevato numero di accessi contemporanei, senza compromettere la velocità di risposta o la stabilità del sistema. Il design architetturale dovrà supportare l'espansione futura, permettendo l'incremento delle risorse in base alle esigenze di crescita dell'utenza.
- [ ] RNF4: Affidabilità: Il sistema deve garantire un'affidabilità, con una disponibilità minima del **95%**, il che corrisponde a un downtime massimo di **18 giorni e 6 ore** all'anno. Il software deve essere progettato per minimizzare i tempi di inattività pianificati e non pianificati, garantendo un accesso continuo ai servizi, anche durante periodi di picco di utilizzo.
- [x] RNF5: Sicurezza e privacy: Il sistema deve aderire ai principi di **Privacy by Design** e **minimizzazione dei dati**, raccogliendo solo le informazioni strettamente necessarie per l'erogazione del servizio (es. Username, email). Tutte le password e i dati sensibili non devono mai essere memorizzati in chiaro. Deve essere imposto l'uso di algoritmi di hashing moderni e sicuri. Tutte le comunicazioni tra client e server devono avvenire esclusivamente tramite protocolli sicuri (HTTPS con TLS 1.2 o superiore).
- [x] RNF6: Accessibilità: Il sistema sarà progettato per garantire un livello di accessibilità di base, aderendo ai requisiti minimi di conformità **WCAG 2.1 (Web Content Accessibility Guidelines) al Livello A**. Questo impegno assicura la rimozione delle barriere all'accessibilità più significative, ponendo le fondamenta per un'interazione fruibile da parte degli utenti con disabilità.
- [x] RNF7: Lingua: Il sistema deve offrire agli utenti la possibilità di cambiare la lingua dell'interfaccia tra una delle seguenti opzioni: Italiano, Inglese e Tedesco. L'utente deve poter selezionare e modificare la lingua preferita in modo intuitivo, e la scelta deve essere mantenuta per le sessioni future.
- [x] RNF8: Facilità d'uso: Il sistema deve garantire un'elevata usabilità ed essere progettato per un'interazione intuitiva, specialmente per utenti con limitata competenza digitale. Il design dell'interfaccia deve essere pulito, coerente e guidare l'utente nel completamento delle operazioni principali.

## 4. Use Case
### Utente anonimo:
RF1: Registrazione
RF2: Login
![[UCD RF1, RF2.drawio.svg]]
#### Use Case RF1: Registrazione
##### Riassunto:
Questo Use case descrive come l'utente anonimo può registrare un nuovo account a cui poi potrà fare login.
##### Descrizione
1. L'utente parte come anonimo e per registrarsi deve cliccare sull'apposito bottone.
2. Nella schermata di registrazione c'è un form i cui campi obbligatori sono: Username, Mail, Password. Mentre i campi opzionali sono: Check disabilità e tipo utente \[eccezione 1] \[estensione 1]
3. Viene mandata una mail con un link per la conferma della registrazione.
4. Cliccando sul link la registrazione viene finalizzata e salvata. \[eccezione 2]
##### Eccezioni
1. Se l'utente non inserisce i campi obbligatori la mail non verrà inviata e la registrazione non potrà proseguire.
2. Se l'utente non usa il link l'utente non viene finalizzato e aggiunto al database.
##### Estensioni
1. Se il tipo dell'utente è operatore o admin prima che la mail di conferma venga inviata chiede l'autorizzazione a un admin per controllare che sia legittimo.
#### Use Case RF2: Login
##### Riassunto:
Questo use case descrive come l’utente anonimo effettua il login nella webapp
##### Descrizione:
1. L'utente visualizza una schermata con un form
2. Se l'utente inserisce all'interno degli appositi campi username e password e preme il pulsante "Login", si apre la schermata principale dell'applicazione \[eccezione 1]
3. Se l'utente (in alternativa a descrizione 2) preme sul pulsante "Login with Google", dovrà inserire le proprie credenziali di Google in apposite schermate per poi arrivare alla pagina principale dell'app \[eccezione 1]
##### Eccezioni:
1. Se l'utente inserisce credenziali errate o inesistenti, si ripresenta nuovamente sulla schermata di login per reinserire quelle corrette

### Utente Base:
RF3: Ricerca
RF4: Visualizzazione mappa
RF7: Richiesta linea dinamica
RF8: Ricevuta di approvazione
RF9: Proposta di alternativa
RF10: Inserimento preferenze
![[UCD RF10, RF3, RF4, RF7, RF8, RF9.drawio.svg]]
#### Use case RF3: Ricerca
##### Riassunto:
Questo use case descrive come l'utente effettua una ricerca sulla webapp
##### Descrizione:
1. L'utente visualizza un'icona con lente d'ingrandimento e una casella in cui può inserire il testo
2. Una volta inserito tutto, l'utente preme il tasto "INVIO" oppure le opzioni sottostanti che coincidono a ciò che soddisfa il parametro di ricerca \[eccezione 1]
##### Eccezioni:
1. Se l'utente inserisce nei parametri di ricerca un luogo che non è stato inserito oppure non esiste, l'app restituisce un errore di "nessun luogo corrispondente alla ricerca"
#### Use case RF4: Visualizzazione mappa
##### Riassunto:
Questo use case descrive come l'utente può interagire con la mappa
##### Descrizione:
1. L'utente visualizzerà la mappa appena aprirà l'applicazione
2. L'utente, per interagire con la mappa dovrà usare il cursore per spostarsi \[estensione 1]
##### Estensioni:
1. Se l'utente vuole avere dei dettagli sul luogo visualizzato sulla mappa, può cliccare su di esso per rivelare informazioni come nome, tipologia (ristorante, parco, università,...) e zona in cui è situato
#### Use case RF7: Richiesta linea dinamica
##### Riassunto:
Questo use case descrive come l'utente può richiedere la tratta per il bus dinamico
##### Descrizione:
1. L'utente preme sul pulsante "RICHIEDI TRATTA" per poter inserire la richiesta del proprio spostamento
2. L'utente dovrà compilare un form inserendo il luogo e l'ora sia del punto di partenza, che quello di arrivo \[eccezione 1] \[estensione 1] \[estensione 3] \[estensione 4]
3. L'utente, una volta inserito tutto il necessario, clicca il pulsante "CONFERMA E INVIA" \[eccezione 2]  \[estensione 2]
##### Eccezioni:
1. Se l'utente inserisce un luogo o un orario non valido (es: partenza da Piazza Venezia alle 10:00 e arrivo al Polo Ferrari Povo 1 alle 10:01), il sistema darà errore e non permetterà l'invio del form fino a quando gli errori non sono stati corretti
2. Se l'utente non cliccherà il pulsante "CONFERMA E INVIA" la richiesta non arriverà agli operatori, di conseguenza non potranno valutare la fattibilità della richiesta.
##### Estensioni:
1. Nel form ci sarà la possibilità di impostare quella tratta come "TRATTA FREQUENTE" e per quali periodi di tempo (esempio: ogni settimana, dal lunedì al venerdì), in modo da dover evitare l'inserimento manuale dello stesso percorso ogni volta
2. Se l'utente desidera cancellare la tratta, può selezionare la richiesta fatta e cliccare sul pulsante "CANCELLA TRATTA"
3. Se l'utente deve prenotare per meno di 10 persone in un unico blocco (es: mamma con i suoi 2 figli), allora dovrà inserire nel form il numero di persone
4. Se l'utente deve prenotare per 10 o più persone (es: insegnante delle elementari con 11 studenti), allora dovrà inserire anche il numero di partecipanti e aspettare che un operatore processi la richiesta
#### Use case RF8: Ricevuta di approvazione
##### Riassunto:
Questo use case descrive come l'utente capisce che la sua richiesta ha effettivamente "attivato" la linea dinamica
##### Descrizione:
1. L'utente riceve una notifica e/o una mail contenente l'esito della richiesta \[eccezione 1] \[estensione 1] \[estensione 2]
##### Eccezioni:
1. Se l'utente non ha effettuato richieste di viaggi e tratte, allora non riceverà alcun tipo di notifica
##### Estensioni:
1. Se la tratta passa nella zona dell'utente, allora riceverà l'esito con la fermata più vicina e l'orario a cui passa
2. Se la tratta non passa nella zona dell'utente, allora riceverà una notifica che propone di visualizzare la linea che è stata approvata e mostrerà anche le alternative disponibili tra le preferenze dell'utente
#### Use case RF9: Proposta di alternativa
##### Riassunto:
Questo use case descrive come l'utente può visualizzare le alternative proposte dall'app
##### Descrizione:
1. L'utente, dopo aver inserito una richiesta di tratta, potrà visualizzare percorsi e veicoli alternativi che soddisfano le richieste e preferenze \[eccezione 1] \[eccezione 2]
2. L'utente potrà poi selezionare ciò che preferisce, in modo che l'applicazione fornisca quel percorso come principale da visualizzare la giornata successiva
##### Eccezioni:
1. Se l'utente non ha selezionato abbastanza preferenze da poter coprire il suo tragitto (es: per il tragitto dell'utente le uniche opzioni possibili sono "bicicletta" e "monopattino", ma ha selezionato solo "autobus"), allora darà un messaggio del tipo: "Viaggio non fattibile in base alle tue preferenze" e farà vedere le tratte calcolate con altri veicoli non preferenziali. 
2. Se l'utente ha richiesto una tratta impossibile da fare con i mezzi disponibili nell'app, allora suggerisce di esplorare alternative che Make Your Move attualmente non copre
#### Use case RF10: Inserimento preferenze
##### Riassunto:
Questo use case descrive come l'utente inserisce le preferenze dei veicoli all'interno dell'app
##### Descrizione:
1. L'utente interagisce con l'apposito menù a tendina e seleziona la voce "PREFERENZE"
2. L'utente seleziona poi i veicoli che preferisce usare e che possiede \[eccezione 1]
##### Eccezioni:
1. Se l'utente non seleziona alcun tipo di preferenze, allora l'applicazione lo avvisa di ciò, ricordandogli di selezionarne almeno una

### Operatore e Admin:
RF5: Richieste utenti
RF6: Statistiche
RF11: Modifiche
RF12: Gestione utenti
![[UCD RF5, RF6, RF11, RF12.drawio.svg]]
#### Use case RF5: Richieste utenti
##### Riassunto:
Questo use case descrive come operatori e admin possono gestire le richieste
##### Descrizione:
1. l'operatore/admin clicca sull'icona apposita per vedere le richieste effettuate dagli utenti
2. l'operatore/admin elabora le richieste, generando la tratta nei momenti e luoghi di richiesta più elevata \[eccezione 1] \[estensione 1]
##### Eccezioni:
1. Se le richieste degli utenti sono poche e/o parecchio sparse in giro per il territorio, allora la tratta dinamica non verrà creata per la giornata successiva
##### Estensioni:
1. Se la richiesta è stata effettuata da una persona affetta da disabilità o per un gruppo consistente di persone (ovvero dalle 10 in su), l'operatore/admin contatterà via mail l'utente per confermare o aggiungere dettagli ulteriori
#### Use case RF6: Statistiche
##### Riassunto:
Questo use case descrive come operatori e admin possono interagire con le statistiche
##### Descrizione:
1. l'operatore/admin clicca sull'icona apposita per vedere le statistiche degli utenti che usufruiscono dell'app
2. Ad operatore/admin si presenteranno diverse viste/grafici per la lettura dei dati che riguarderanno zona, ora (sia di partenza che di arrivo) e modalità usata per la mobilitazione \[estensione 1]
##### Estensioni:
1. Se operatore/admin desidera visualizzare nel dettaglio i singoli utenti e che meta effettuano spesso, può selezionare il singolo utente per vedere le sue statistiche
#### Use case RF11: Modifiche
##### Riassunto:
Questo use case descrive come l'admin possa effettuare modifiche all'applicazione
##### Descrizione:
1. L'admin clicca sul pulsante per accedere al database
2. Una volta nel database, l'admin può aggiungere, modificare e cancellare fermate, stazioni di biciclette e monopattini \[estensione 1]
##### Estensioni:
1. Se le modifiche sono da apportare alle fermate, allora esiste anche l'opzione di disabilitarle temporaneamente
#### Use case RF12: Gestione utenti
##### Riassunto:
Questo use case descrive come gli admin possano gestire gli utenti e i relativi permessi
##### Descrizione:
1. L'admin clicca sul pulsante per accedere al database
2. Una volta nel database, l'admin può aggiungere, modificare e cancellare utenti base, operatori e altri admin \[eccezione 1]
##### Eccezioni:
1. L'admin non può modificare permessi a se stesso
## 5. User Story
### User Story 1 - Associata allo Use Case RF1: Registrazione
#### Scelta tra credenziali locali o autenticazione tramite Google
Come utente, operatore o admin, voglio registrarmi con credenziali locali o con il sistema di autenticazione di Google in modo da scegliere quello che preferisco
#### Criteri di accettazione
- Tutti i tipi di utente possono scegliere tra la registrazione con Google o in locale
- Dopo una registrazione riuscita viene inviata la mail e si viene reindirizzati alla schermata di login
- Se avviene una registrazione errata (es. caratteri non ammessi o account Google non esistente) devono apparire messaggi di errore adeguati.
#### TASKS - User Story 1
1. Integrare entrambe le opzioni di registrazione (locale, Google)
2. Configurare il flusso decisionale della registrazione
3. Gestire le azioni da fare dopo che la registrazione va a buon fine
4. Testare che entrambe le registrazioni vadano a buon fine
5. Implementare i messaggi di errore per ogni metodo
### User Story 2 - Associata allo Use Case RF2: Login
#### Scelta tra credenziali locali o autenticazione tramite Google
Come utente, operatore o admin, voglio effettuare login con credenziali locali o con il sistema di autenticazione di Google in modo da scegliere quello che preferisco
#### Criteri di accettazione
- Tutti i tipi di utente possono scegliere tra l'accesso con Google o in locale
- Dopo un accesso riuscito si viene indirizzati alla schermata principale dell'applicazione
- Se avviene un login errato (es. caratteri non ammessi o account non registrato) devono apparire messaggi di errore adeguati.
#### TASKS - User Story 2
1. Integrare entrambe le opzioni di accesso (locale, Google)
2. Configurare il flusso decisionale dell'accesso
3. Gestire le azioni da fare dopo che l'accesso va a buon fine
4. Testare che entrambe le modalità di accesso vadano a buon fine
5. Implementare i messaggi di errore per ogni metodo
### User Story 3 - Associata allo Use Case RF3: Ricerca
#### Ricerca di luoghi e stazioni
Come utente voglio effettuare una ricerca in modo da selezionare il luogo per la tratta
#### Criteri di accettazione
- Tutti i tipi di utente possono cercare le stazioni e i luoghi
- Tutti i luoghi e tutte le stazioni devono poter essere cercate
- Il sistema restituisce una lista di risultati coerente ai criteri di ricerca inseriti
- Se non vengono trovati risultati, devono apparire messaggi informativi adeguati.
#### TASKS - User Story 3
1. Creare il campo di ricerca nella UI, aggiungendo placeholder e istruzioni per renderlo più intuitivo all'utente
2. Implementare la logica di ricerca
3. Recuperare e visualizzare i risultati della ricerca
4. Testare la funzionalità di ricerca
5. Gestire i casi senza risultati
### User Story 4 - Associata allo Use Case RF4: Mappa
#### Visualizzazione e interazione con la mappa
Come utente voglio visualizzare una mappa interattiva in modo da scegliere fermate e vedere i percorsi generati
#### Criteri di accettazione
- Tutti i tipi di utente possono visualizzare e interagire con la mappa
- Tutti i punti di interesse devono poter essere visualizzati ed essere interagibili dalla mappa
#### TASKS - User Story 4
1. Integrare la mappa nella UI dell'applicazione
2. Gestire le azioni dopo l'interazione del punto d'interesse
3. Testare le funzionalità della mappa
### User Story 5 - Associata allo Use Case RF5: Richieste utenti
#### Gestione delle richieste effettuate dagli utenti
Come operatore e admin voglio visualizzare e gestire le richieste in modo da poterle accettare generare la tratta di conseguenza
#### Criteri di accettazione
- Solo operatori e admin possono visualizzare e gestire le richieste degli utenti
- Solo le richieste "future", ovvero compilate per una tratta ancora da generare, possono essere modificate, accettate o revocate
- Se le richieste non raggiungono un numero di utenti adeguato o sono troppo sparsi in giro per il territorio, devono apparire messaggi informativi riguardo la "non fattibilità" della tratta
#### TASKS - User Story 5
1. Integrare la visualizzazione delle richieste nella UI
2. Dare la possibilità di modifica, accettazione e revoca della richiesta
3. Testare le funzionalità di modifica, accettazione e revoca
4. Implementare messaggi di errore per ogni metodo
### User Story 6 - Associata allo Use Case RF6: Statistiche
#### Visualizzazione delle statistiche
Come operatore e admin voglio visualizzare le statistiche dell'app come fermate o tratte più comuni e i veicoli preferiti degli utenti.
#### Criteri di accettazione
- Solo operatori e admin possono visualizzare le statistiche
- Le statistiche devono essere facilmente interpretabili da chiunque debba visualizzarle
- I dati delle statistiche devono essere aggregati e visualizzati in modo opportuno
#### TASKS - User Story 6
1. Integrare la visualizzazione delle statistiche nella UI tramite dashboard
2. Inserire un filtraggio/ricerca dei dati nella dashboard
3. Costruire la dashboard in modo che i grafici e dati non si sovrappongano
4. Testare che le statistiche vengano visualizzate correttamente
### User Story 7 - Associata allo Use Case RF7: Richiesta linea dinamica
#### Gestione richiesta della Tratta
Come utente voglio poter aprire una richiesta per agevolare un mio spostamento nel futuro in modo da poter avere un'ottimizzazione sul il mio spostamento.
#### Criteri di accettazione
- Tutti gli utenti devono poter richiedere una tratta
- Nel form devo poter inserire la partenza/arrivo, l'ora di partenza e i veicoli preferiti
- Il form deve essere intuitivo per gli utenti
- La richiesta deve essere inviata agli operatori per l'accettazione
- Il sistema deve dare errore se la tratta creata o non va a buon fine o il form è compilato in modo errato
#### TASKS - User Story 7
1. Creare il form della richiesta
2. Inserire la ricerca per le stazioni/zone
3. Testare la corretta creazione delle richieste
4. Testare che le Richieste arrivino agli operatori
5. Dare messaggi di errore se le tratte non vengono create nel modo corretto
### User Story 8 - Associata allo Use Case RF8: Ricevuta di Approvazione
#### Gestione Ricevuta di consegna
Come utente voglio sapere se la mia richiesta è stata approvata e sapere l'itinerario del bus, e se non è stato approvato ricevere un'alternativa
#### Criteri di accettazione
- Solo gli utenti base possono ricevere l'esito della domanda
- Inviare in automatico una mail ai richiedenti quando la tratta del giorno dopo viene finalizzata
- La mail deve essere costruita secondo l'esito della richiesta (Positivo o Negativo)
- La web app deve anche inviare una notifica agli utenti indicando luogo e orario del passaggio se la richiesta risulta positiva
- Se la richiesta è negativa la mail deve inserire un bottone per la possibilità di richiedere un metodo alternativo di spostamento (Secondo le preferenze)
#### TASKS - User Story 8
1. Creare una routine che crei le mail e le invii
2. Inviare anche una notifica per rinforzare la mail
3. Testare che le mail vengano create e inviate nel modo corretto
4. Testare che le notifiche vengano effettivamente ricevute
### User Story 9 - Associata allo Use Case RF9: Proposta di alternativa
#### Proposta di alternativa
Come utente voglio ricevere alternative in modo da non perdere tempo se la richiesta non sarà in mio favore
#### Criteri di accettazione
- Solo gli utenti base possono avere la proposta di alternativa
- La proposta dovrà includere tutti i veicoli disponibili nell'app, dando priorità a quelli selezionati come preferiti dall'utente
- Se i veicoli preferiti non sono idonei per il percorso da fare, allora verrà generato un messaggio informativo opportuno, mostrandone altri anche se non sono stati selezionati dall'utente
#### TASKS - User Story 9
1. Includere i veicoli in alternativa alla linea dinamica
2. Visualizzare il percorso sulla mappa
3. Gestire le azioni da fare dopo che un'alternativa è stata selezionata
4. Testare che l'erogazione e la selezione delle alternative vada a buon fine
### User Story 10 - Associata allo Use Case RF10: Inserimento preferenze
#### Impostazione preferenze
Come utente voglio salvare i mezzi preferiti in modo da ottenere soluzioni più adatte a me
#### Criteri di accettazione
- Solo gli utenti base possono impostare le preferenze
- Tutti i veicoli devono poter essere selezionati come preferenziali in contemporanea
- Se non sono stati selezionati veicoli tra le preferenze, allora verrà generato un messaggio informativo opportuno, invitando a prenderne in considerazione almeno uno per usufruire dell'app a pieno
#### TASKS - User Story 10
1. Includere nella UI una scheda contenente la lista dei veicoli disponibili
2. Dare la possibilità di salvare i veicoli come preferenziali
3. Testare che la selezione dei veicoli funzioni
### User Story 11 - Associata allo Use Case RF11: Modifiche
#### Modifiche parametri di sistema
Come admin voglio modificare fermate, tratte e preferenze di sistema per gestire in modo ottimale il flusso
#### Criteri di accettazione
- Solo gli admin possono mettere mano ai parametri di sistema
- Tutte le modifiche, una volta applicate, devono essere visualizzabili dagli utenti e dagli operatori
- Tutte le modifiche, se applicate per errore, devono poter essere revocabili dall'admin
#### TASKS - User Story 11
1. Includere nella UI una scheda apposita per la gestione dei parametri di sistema
2. Gestire le azioni da fare dopo che un admin decide di modificare un parametro
3. Testare che le modifiche vengano effettuate e che siano visualizzabili da utenti e operatori
### User Story 12 - Associata allo Use Case RF12: Gestione Utenti
#### Gestione permessi e ruoli
Come admin voglio poter gestire ruoli e autorizzazioni in modo da mantenere il sistema sicuro e operativo
#### Criteri di accettazione
- Solo gli admin possono mettere mano ai permessi
- Tutti gli utenti devono essere visualizzabili e modificabili dagli admin
- Gli admin possono modificare i permessi ad utenti, operatori e altri admin, ma non a se stesso. In tal caso comparirà un messaggio di errore adeguato al contesto
#### TASKS - User Story 12
1. Includere nella UI una scheda apposita per la gestione degli utenti
2. Inserire gli utenti in un database
3. Testare che le modifiche vengano effettuate
### User Story 13 - Associata allo Use Case RF7: Richiesta linea dinamica
#### Richiesta di tratta per utenti affetti da disabilità
Come utente con disabilità motorie o sensoriali voglio poter richiedere una tratta in modo usufruire dei servizi dell'app senza barriere o difficoltà aggiuntive
***N.B: Questa User Story è da considerarsi come estensione della User Story 7. Pertanto i Criteri di accettazione e le tasks descritti sotto sono un'aggiunta a quelli già presenti***
#### Criteri di accettazione
- L'interfaccia utente deve essere conforme agli standard WCAG 2.1 livello A
- Il sistema deve dare errore se la tratta creata o non va a buon fine o il form è compilato in modo errato. Anche gli errori devono essere opportunamente segnalati seguendo lo standard WCAG 2.1 livello A
#### TASKS - User Story 13
6. Assicurarsi che i font siano ridimensionabili senza compromettere o perdere il layout
7. Fare in modo di coinvolgere più sensi per i messaggi di errore (es: vista e suono)
8. Testare l'interazione con strumenti di accessibilità come lo zoom
## 6\. Epiche
### Epica 1 - Richiesta della tratta dinamica
#### User Stories associate:
- User Story 7: Richiesta linea dinamica
- User Story 8: Gestione Ricevuta di consegna
- User Story 13: Richiesta di tratta per utenti affetti da disabilità
#### Descrizione:
L'Epica 1 comprende tutte le funzionalità che permettono agli utenti di richiedere la tratta in base a scenari ed esigenze differenti
#### Motivazione:
Questa epica è centrale per Make Your Move, in quanto verte sulla funzionalità principale dell'app
## 7\. Front-end design
### Figura 1: schermata di registrazione
![[Registrazione.png]]
Figura 1 mostra il mockup della schermata di registrazione dell'applicazione "Make Your Move" (raggiungibile tramite un pulsante "REGISTRATI" aggiungibile in Figura 2), che rappresenta come l'interfaccia si presenterà all'utente finale. Di seguito una descrizione riguardante i requisiti funzionali e non funzionali precedentemente definiti:
#### RF1: Registrazione
La registrazione può avvenire in 2 modi:
- Tramite credenziali locali: l'interfaccia permette all'utente di inserire username, email e password, selezionare il tipo di utente (tra i disponibili abbiamo utente base, operatore e admin) e se possiede eventuali disabilità che richiedono una particolare attenzione nell'usufruire dei servizi forniti
- Tramite account Google: cliccando il pulsante con l'icona di Google, l'interfaccia permette di raccogliere le informazioni necessarie in modo da compilare i campi. Quelli rimanenti, ovvero tipo utente e disabilità, saranno da compilare manualmente per ultimare la registrazione
#### RNF1: Compatibilità
L'interfaccia, essendo basata su un'applicazione web, è progettata per essere utilizzata su diversi browser (come specificato nel requisito), e il design pulito e semplice supporta la compatibilità con browser come Chrome, Opera ed Edge
#### RNF5: Sicurezza e privacy
Il sistema raccoglie solo le informazioni personali che si possono vedere da figura 1, garantendo così ciò che è stato descritto in RNF5
#### RNF6: Accessibilità
Da come si può notare in figura 1, l'interfaccia permette di selezionare una spunta per utenti possessori di disabilità o invalidità che necessitano di particolari sostegni o supporti
#### RNF8: Facilità d'uso
La disposizione dei campi sono intuitivi e facili da individuare. L'accesso rapido tramite Google è chiaramente visibile. Questi elementi favoriscono l'utilizzo senza bisogno di istruzioni complesse, come richiesto in RNF8, permettendo all'utente di familiarizzare con il sistema in poco tempo
### Figura 2: schermata di login
![[Login.png]]
Figura 2 mostra il mockup dell'interfaccia della schermata di login dell'applicazione. Di seguito una descrizione riguardante i requisiti funzionali e non funzionali precedentemente definiti:
#### RF2: Login
L'accesso può avvenire in 2 modi:
- Tramite credenziali locali: l'interfaccia permette all'utente di inserire username e password, in modo da poter entrare nell'applicazione
- Tramite account Google: cliccando il pulsante con l'icona di Google, l'interfaccia permette di utilizzare le proprie credenziali Google per poter accedere
#### RNF1: Compatibilità
L'interfaccia, essendo basata su un'applicazione web, è progettata per essere utilizzata su diversi browser (come specificato nel requisito), e il design pulito e semplice supporta la compatibilità con browser come Chrome, Opera ed Edge
#### RNF7: Lingua
Sebbene non specificato direttamente nell'immagine, il design potrebbe facilmente supportare la funzionalità di cambio lingua (es. aggiungendo un selettore di lingua nell'angolo), permettendo all'utente di scegliere tra Italiano, Inglese o Tedesco, come descritto in RNF7
#### RNF8: Facilità d'uso
La disposizione dei campi sono intuitivi e facili da individuare. L'accesso rapido tramite Google è chiaramente visibile. Questi elementi favoriscono l'utilizzo senza bisogno di istruzioni complesse, come richiesto in RNF8, permettendo all'utente di familiarizzare con il sistema in poco tempo
### Figura 3: schermata principale Make Your Move (Utente base)
![[Mappa.png]]
Figura 3 mostra il mockup dell'interfaccia dell'applicazione per l'utente base. Sulla sinistra è presente una casella di ricerca e un pulsante "Richiedi Tratta" per inserire la propria richiesta (vedi figura 6). Al centro si può visualizzare e interagire con una mappa. Sulla destra si possono vedere dei pulsanti per vedere varie "viste" (piste ciclabili, percorsi autobus,....) e per accedere alle impostazioni. Di seguito una descrizione riguardante i requisiti funzionali e non funzionali precedentemente definiti:
#### RF3: Ricerca
L'interfaccia permette all'utente di poter effettuare ricerche di stazioni, zone e fermate
#### RF4: Visualizzazione mappa
L'interfaccia permette all'utente di poter visualizzare ed interagire con la mappa centrale, sia con i pulsanti sul lato destro, sia interagendo con il cursore e con la casella di ricerca
#### RF7: Richiesta linea dinamica
Grazie al pulsante sulla sinistra, l'utente può effettuare una richiesta per la tratta dinamica
#### RNF1: Compatibilità
L'interfaccia, essendo basata su un'applicazione web, è progettata per essere utilizzata su diversi browser (come specificato nel requisito), e il design pulito e semplice supporta la compatibilità con browser come Chrome, Opera ed Edge
#### RNF8: Facilità d'uso
La disposizione dei campi sono intuitivi e facili da individuare. Questi elementi favoriscono l'utilizzo senza bisogno di istruzioni complesse, come richiesto in RNF8, permettendo all'utente di familiarizzare con il sistema in poco tempo
### Figura 4: schermata principale Make Your Move (Operatore)
![[MappaOperatore.png]]
Figura 4 mostra la schermata che si presenta se l'utente che usa l'app è di tipo "operatore". Da come si può osservare, l'interfaccia è molto simile a quella dell'utente base, con la differenza di 2 pulsanti sulla sinistra. Di seguito una descrizione riguardante i requisiti funzionali e non funzionali precedentemente definiti:
#### RF5: Richieste utenti
Il pulsante "Controlla richieste" permette all'operatore di processare le richieste di tratta effettuate dagli utenti
#### RF6: Statistiche
Il pulsante "Statistiche" permette all'operatore di visualizzare le statistiche riguardanti gli utilizzatori dell'app (zona di arrivo, destinazione, orari di partenza,...)
#### RNF1: Compatibilità
L'interfaccia, essendo basata su un'applicazione web, è progettata per essere utilizzata su diversi browser (come specificato nel requisito), e il design pulito e semplice supporta la compatibilità con browser come Chrome, Opera ed Edge
#### RNF8: Facilità d'uso
La disposizione dei campi sono intuitivi e facili da individuare, come richiesto in RNF8, permettendo all'operatore di aver bisogno di un tempo molto breve per la formazione
### Figura 5: schermata principale Make Your Move (Admin)
![[MappaAdmin.png]]
Figura 5 mostra la schermata che si presenta se l'utente che usa l'app è di tipo "admin". Da come si può osservare, l'interfaccia è molto simile a quella dell'operatore, con l'aggiunta di 2 pulsanti sulla sinistra. Di seguito una descrizione riguardante i requisiti funzionali e non funzionali precedentemente definiti:
#### RF11: Modifiche
Il pulsante "Modifica fermate" permette all'admin di interagire ed applicare modifiche visibili a tutti. Per esempio l'admin può segnare una fermata come "temporaneamente sospesa" a causa di lavori
#### RF12: Gestione utenti
il pulsante "Gestisci utenti" permette agli admin di gestire i ruoli degli utenti che sono presenti sull'app e di cancellarli in caso di comportamenti poco consoni
#### RNF1: Compatibilità
L'interfaccia, essendo basata su un'applicazione web, è progettata per essere utilizzata su diversi browser (come specificato nel requisito), e il design pulito e semplice supporta la compatibilità con browser come Chrome, Opera ed Edge
#### RNF6: Accessibilità
L'interfaccia permette, se preventivamente segnalato al momento della registrazione, di far valutare la richiesta più attentamente ad un operatore o admin
#### RNF8: Facilità d'uso
La disposizione dei campi sono intuitivi e facili da individuare. Questi elementi favoriscono l'utilizzo senza bisogno di istruzioni complesse, come richiesto in RNF8, permettendo all'utente di familiarizzare con il sistema in poco tempo
### Figura 6: richiesta tratta
![[Richiesta.png]]
Figura 6 mostra il mockup della schermata di richiesta tratta, raggiungibile dopo aver premuto il relativo pulsante in figura 3. L'interfaccia è espandibile includendo elementi di funzionalità discusse negli Use Case e nelle User Stories come:
- Calendario per richiedere una tratta per giorni successivi a quello odierno
- Pulsante per salvare la tratta e dare un'opzione per la frequenza (es: tutti i giorni, solo dal lunedì al venerdì)
- Box per scrivere il numero di richiedenti
Di seguito una descrizione riguardante i requisiti funzionali e non funzionali precedentemente definiti:
#### RF7: Richiesta tratta
L'utente può inserire la zona di partenza (con relativo orario) e quella di arrivo nell'interfaccia. Come anticipato prima, questa è espandibile con elementi/funzionalità già descritte in precedenza, che però non sono descritte dalla figura
#### RF8: Ricevuta di approvazione
Una volta cliccato il pulsante di conferma, l'utente dovrà attendere che un operatore o un admin processi la richiesta e generi la tratta. Nel caso passasse nella zona dell'utente, riceverà una mail o notifica a riguardo
#### RF9: Proposta di alternativa
Il sistema, specialmente nei casi in cui la tratta non passa nella zona dell'utente o se non l'ha richiesta, suggerirà tramite mail o notifica di visionare le alternative proposte dall'app
#### RNF1: Compatibilità
L'interfaccia, essendo basata su un'applicazione web, è progettata per essere utilizzata su diversi browser (come specificato nel requisito), e il design pulito e semplice supporta la compatibilità con browser come Chrome, Opera ed Edge
#### RNF8: Facilità d'uso
La disposizione dei campi sono intuitivi e facili da individuare. Questi elementi favoriscono l'utilizzo senza bisogno di istruzioni complesse, come richiesto in RNF8, permettendo all'utente di familiarizzare con il sistema in poco tempo
### Figura 7: impostazioni
![[Settings.png]]
Figura 7 mostra il mockup delle impostazioni, raggiungibili da un pulsante presente nelle figure 3, 4 e 5. Il pulsante "Impostazioni Account" permette di modificare aspetti come lo username e informazioni relative ad utenti con particolari bisogni, "Preferenze veicoli" manda all'interfaccia di figura 8 e "Reimposta password" permette di cambiare la password. Di seguito una descrizione riguardante i requisiti funzionali e non funzionali precedentemente definiti:
#### RNF1: Compatibilità
L'interfaccia, essendo basata su un'applicazione web, è progettata per essere utilizzata su diversi browser (come specificato nel requisito), e il design pulito e semplice supporta la compatibilità con browser come Chrome, Opera ed Edge
#### RNF7: Lingua
Sebbene non specificato direttamente nell'immagine, il design potrebbe facilmente supportare la funzionalità di cambio lingua (es. aggiungendo un selettore di lingua nell'angolo), permettendo all'utente di scegliere tra Italiano, Inglese o Tedesco, come descritto in RNF7
#### RNF8: Facilità d'uso
La disposizione dei campi sono intuitivi e facili da individuare. Questi elementi favoriscono l'utilizzo senza bisogno di istruzioni complesse, come richiesto in RNF8, permettendo all'utente di familiarizzare con il sistema in poco tempo
### Figura 8: preferenze veicoli
![[Preferenze.png]]
L'interfaccia di figura 8, raggiungibile tramite un pulsante in figura 7, permette di selezionare i veicoli che vogliamo utilizzare e visualizzare dall'app. Di seguito una descrizione riguardante i requisiti funzionali e non funzionali precedentemente definiti:
#### RF10: Inserimento preferenze
L'interfaccia permette all'utente di selezionare contemporaneamente più veicoli, in modo che possa ricevere alternative coerenti alle sue scelte
#### RNF1: Compatibilità
L'interfaccia, essendo basata su un'applicazione web, è progettata per essere utilizzata su diversi browser (come specificato nel requisito), e il design pulito e semplice supporta la compatibilità con browser come Chrome, Opera ed Edge
#### RNF8: Facilità d'uso
La disposizione dei campi sono intuitivi e facili da individuare. Questi elementi favoriscono l'utilizzo senza bisogno di istruzioni complesse, come richiesto in RNF8, permettendo all'utente di familiarizzare con il sistema in poco tempo
## 8\. User Flow
