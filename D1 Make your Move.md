
## Dipartimento di Ingegneria e Scienza dell’Informazione

| **Progetto:**             | **Make your Move**          |
| ------------------------- | --------------------------- |
| **Titolo del documento:** | **Descrizione di Progetto** |
 
**Document Info**

| Doc. Nam        | D1-DescrizioneProgetto                                                                 |
| :-------------- | :------------------------------------------------------------------------------------- |
| **Description** | Documento di analisi dei requisiti funzionali, non funzionali, user story e front-end. |
| **Doc. Number** | D1 V0.4                                                                                |

## Indice

1. Il progetto Make your Move
2. Requisiti Funzionali
3. Requisiti Non Funzionali
4. Use case Diagram

## 1\. Il progetto Make your Move

![[1_Problematiche.jpg]]
Il problema che abbiamo identificato riguarda una macro-categoria, ovvero traffico e viabilità. A Trento, per esempio, non è difficile trovare strade congestionate (specialmente in fasce orarie "di punta") a causa del traffico che talvolta diventa anche insostenibile (sia a livello di inquinamento ambientale, che a livello di disagio del cittadino).
Effettuando interviste ad amici e parenti, abbiamo notato che, chi vorrebbe utilizzare mezzi di trasporto pubblici, non si trova in una posizione da poter essere incentivato ad usarli. Infatti, a detta loro, il traffico eccessivo comporta un rallentamento del mezzo, accumulando ritardo di conseguenza. Specialmente per chi non si può permettere di arrivare a destinazione in ritardo o per chi deve effettuare troppi cambi, si andrà a preferire il mezzo personale, causando così un "loop" che non avrà fine.
Abbiamo inoltre osservato che, per quanto riguarda la questione degli autobus, la domanda non è sempre concerne all'offerta. Entrando più nel dettaglio si può notare come ci siano abbastanza spesso situazioni di questo tipo:
- Pochi autobus ma molto pieni. Alcune persone devono aspettare il prossimo perchè non sono riuscite a salire a causa di ciò
- Molti autobus quasi vuoti. Queste potrebbero essere risorse ricollocabili altrove, dove c'è un reale bisogno

![[2_Soluzione.jpg]]
Il progetto ha come obiettivo la realizzazione di un’applicazione web per aiutare i cittadini a spostarsi nel comune di Trento. Make Your Move consiste infatti nella creazione di tratte per gli autobus a livello dinamico. La tratta verrà decisa la sera prima in base alle segnalazioni raccolte dagli utenti, ovvero Il punto di partenza, quello di arrivo e i relativi orari. Arriverà poi una notifica all'utente su quale sarà il suo bus, dove e quando giungerà

### Q&A:
- *Non è confusionario il fatto che delle linee verranno modificate ogni giorno?*
- Make your Move non andrà a modificare tratte già preesistenti, ma verrà creata una linea apposita (nome in codice, "linea D") in modo da generare meno confusione possibile, specialmente tra i nostri utenti più abitudinari :)
- *Se mi dimentico di inserire la tratta per il giorno successivo come faccio ad arrivare a destinazione? Mi tocca per forza usare il mezzo personale?*
- Non necessariamente. Make your Move salva le tratte che l'utente ha considerato come "abitudinarie". In caso il percorso desiderato sia "straordinario" e/o l'utente si è dimenticato di inserirlo, l'applicazione propone (in base a disponibilità e preferenze) mezzi pubblici alternativi come linee autobus tradizionali, monopattini elettrici, biciclette,... Il veicolo personale (inteso come auto o moto) resterà disponibile come ultima spiaggia. In tal caso Make Your Move fornirà un percorso, dove possibile, in zone meno trafficate con simile tempo di arrivo (Eta. max 5 min in più considerando le condizioni di traffico attuali sul tragitto più breve)
- *Sono un utente con disabilità fisiche. L'applicazione può adattarsi alle mie esigenze?*
- Certamente! Make Your Move al momento della registrazione chiederà le preferenze dei veicoli che l'applicazione offre, in modo che sia utenti con bisogni speciali che persone che semplicemente provano un odio profondo verso alcune opzioni, possano personalizzare i loro percorsi con serenità

![[3_Vantaggi.jpg]]
### Pro e Contro
I vantaggi che si otterranno con l'utilizzo della webapp sono molteplici.
Per il comune:
- Miglioramento della viabilità: le zone più soggette a traffico saranno meno congestionate a causa della minor presenza di mezzi personali e di percorsi alternativi suggeriti
- Minor impatto ambientale: sempre a causa di meno auto e moto presenti su strada, l'inquinamento dell'aria sarà in diminuzione
- Costi minori: ottimizzando l'uso dei veicoli pubblici in base alle richieste degli utenti, i costi di mantenimento saranno più contenuti

Per il cittadino:
- Meno disagi: gestendo i veicoli in modo più controllato, è più difficile che i cittadini subiscano disagi per ritardi, affollamenti e congestionamenti
- Ritardi più contenuti: sempre per la minor presenza di veicoli su strada, è più probabile che gli autobus arrivino in orario alle fermate previste (o che comunque, il ritardo difficilmente sia attribuibile al traffico)
- Accesso remoto: grazie all'interfaccia web accessibile da tutti i dispositivi, Make your Move è accessibile dove e quando si vuole
- Notifiche/promemoria: l'applicazione manda notifiche all'utente dell'itinerario creato per il giorno successivo, in modo che non si debba necessariamente entrare nell'app solo per questo motivo

### Limiti dell'applicazione:
- Dipendenza da una connessione internet: La nostra webapp necessita di una connessione internet per poter usufruire delle funzionalità
- Accessibilità limitata per utenti non digitali: Make your Move, nonostante sia fornito di tutorial introduttivo, potrebbe non essere utilizzabile a pieno per utenti non avvezzi al digitale sia perchè risulta troppo complesso, sia perchè non possiedono strumenti compatibili con l'applicazione
- Poche possibilità per gli utenti con disabilità: L'app non è usufruibile a pieno da utenti affetti da determinate disabilità, rendendo quindi alcune possibilità/alternative non fattibili 
- Manutenzione e aggiornamenti: La webapp non sarà usufruibile sempre a causa di manutenzioni programmate, che comunque non supereranno il quantitativo di tempo prestabilito (RNF4)
- Sicurezza e Privacy: sebbene l'applicazione sia stata progettata rispettando norme di sicurezza e privacy nei confronti dell'utente, non è comunque esente dal rischio di potenziali attacchi e violazioni informatiche, compromettendo di conseguenza i dati sensibili inseriti
- Integrazione con sistemi esistenti: la compatibilità e l'integrazione futura con sistemi esistenti potrebbe risultare difficoltosa con sistemi attualmente in uso 
- Dipendenza dall'infrastruttura tecnica: Le prestazioni dell'applicazioni dipendono dalla qualità e dalla capacità dei server. Di conseguenza, se l'hardware non soddisfa queste due proprietà, potrebbero presentarsi problemi sul servizio (N.B: RNF2 è stato scritto presupponendo che l'hardware sia adeguato per le richieste)
- Possibili costi iniziali per il comune e per Trentino Trasporti: l'implementazione del servizio può comportare un piccolo investimento iniziale riguardo la formazione del personale, l'investimento di nuove risorse e la possibile integrazione con sistemi già esistenti

## 2. Requisiti Funzionali
### Requisiti funzionali comuni ad Admin e Utente Base
- [x] RF1: Registrazione: Il sistema deve permettere agli utenti di registrarsi utilizzando mail e un nickname, garantendo così lo pseudo-anonimato (RNF5) e far in modo di tenere traccia di tratte e veicoli preferiti (RF7 e RF10)
- [x] RF2: Login: Il sistema deve permettere agli utenti di poter accedere col proprio account creato precedentemente (RF1) così da poter accedere ai propri dati salvati e per poter far riconoscere le richieste dei servizi al server
- [x] RF3: Ricerca: L'utente deve poter effettuare ricerche dei luoghi per indicare il punto di partenza e arrivo
- [x] RF4: Visualizzazione mappa: L'utente deve essere in grado di visualizzare e interagire con la mappa interattiva

### Requisiti funzionali Admin
- [ ] RF5: Richieste utenti: Il sistema deve garantire agli admin di visualizzare in blocco le richieste di tratte effettuate dagli utenti (RF7)
- [ ] RF6: Statistiche: Il sistema deve poter permettere agli admin di visualizzare le statistiche riguardanti le richieste e le persone effettivamente salite

### Requisiti funzionali Utente
- [x] RF7: Richiesta tratta: Il sistema deve permettere all'utente di richiedere il punto di partenza e di arrivo, con i relativi orari
- [x] RF8: Ricevuta di consegna: Il sistema, una volta che genera la tratta della linea dinamica, deve fornire una risposta all'utente, dichiarando dove e quando si troverà il bus
- [x] RF9: Proposta di alternativa: Il sistema, se la tratta è satura o la generazione di questa risulta troppo lontana dall'utente, deve fornire un'alternativa valida in base a disponibilità e preferenze (RF10)
- [x] RF10: Inserimento preferenze: Il sistema deve consentire all'utente di inserire i veicoli preferenziali

## 3. Requisiti Non Funzionali
- [ ] RNF1: Compatibilità: Il sistema deve essere compatibile con i seguenti browser: Chrome (inserisci versione) e Firefox (inserisci versione)
- [ ] RNF2: Performance: Il sistema deve garantire tempi di risposta entro 5 secondi
- [ ] RNF3: Scalabilità: Il sistema deve essere in grado di integrare future espansioni senza troppe difficoltà
- [ ] RNF4: Affidabilità: Il sistema dovrà garantire dei tempi di esecuzione di almeno 15h filate, con un massimo di 2h di "down-time" per manutenzione programmata
- [ ] RNF5: Sicurezza e privacy: Il sistema dovrà garantire uno pseudo-anonimato nella raccolta delle informazioni necessarie (Nickname e mail) 
- [ ] RNF6: Accessibilità: Il sistema deve essere usufruibile da utenti affetti da disabilità
- [ ] RNF7: Lingua: Il sistema sarà in Italiano e in Inglese
- [ ] RNF8: Facilità d'uso: Il sistema, grazie ad un tutorial introduttivo, deve essere facilmente fruibile anche per utenti poco avvezzi all'uso di internet e dello smartphone

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
RF7: Richiesta tratta
RF8: Ricevuta di consegna
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
#### Use case RF7: Richiesta tratta
##### Riassunto:
Questo use case descrive come l'utente può richiedere la tratta per il bus dinamico
##### Descrizione:
1. L'utente preme sul pulsante "RICHIEDI TRATTA" per poter inserire la richiesta del proprio spostamento
2. L'utente dovrà compilare un form inserendo il luogo e l'ora sia del punto di partenza, che quello di arrivo \[eccezione 1] \[estensione 1] 
3. L'utente, una volta inserito tutto il necessario, clicca il pulsante "CONFERMA E INVIA" \[eccezione 2]  \[estensione 2]
##### Eccezioni:
1. Se l'utente inserisce un luogo o un orario non valido (es: partenza da Piazza Venezia alle 10:00 e arrivo al Polo Ferrari Povo 1 alle 10:01), il sistema darà errore e non permetterà l'invio del form fino a quando gli errori non sono stati corretti
2. Se l'utente non cliccherà il pulsante "CONFERMA E INVIA" la richiesta non arriverà agli operatori, di conseguenza non potranno valutare la fattibilità della richiesta.
##### Estensioni:
1. Nel form ci sarà la possibilità di impostare quella tratta come "TRATTA FREQUENTE" e per quali periodi di tempo (esempio: ogni settimana, dal lunedì al venerdì), in modo da dover evitare l'inserimento manuale dello stesso percorso ogni volta
2. Se l'utente desidera cancellare la tratta, può selezionare la richiesta fatta e cliccare sul pulsante "CANCELLA TRATTA"
#### Use case RF8: Ricevuta di consegna
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

