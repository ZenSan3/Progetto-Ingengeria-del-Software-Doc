
## Dipartimento di Ingegneria e Scienza dell’Informazione

| **Progetto:**             | **Make your Move**          |
| ------------------------- | --------------------------- |
| **Titolo del documento:** | **Descrizione di Progetto** |
 
**Document Info**

| Doc. Nam        | D1-DescrizioneProgetto                                                                 |
| :-------------- | :------------------------------------------------------------------------------------- |
| **Description** | Documento di analisi dei requisiti funzionali, non funzionali, user story e front-end. |
| **Doc. Number** | D1 V0.3                                                                                |

## Indice

1. Il progetto Make your Move
2. Requisiti Funzionali
3. Requisiti Non Funzionali

## 1\. Il progetto Make your Move

![[1_Problematiche.jpg]]
Il problema che abbiamo identificato riguarda una macro-categoria, ovvero traffico e viabilità. A Trento, per esempio, non è difficile trovare strade congestionate (specialmente in fasce orarie "di punta") a causa del traffico che talvolta diventa anche insostenibile (sia a livello di inquinamento ambientale, che a livello di disagio del cittadino).
Effettuando interviste ad amici e parenti, abbiamo notato che, chi vorrebbe utilizzare mezzi di trasporto pubblici, non si trova in una posizione da poter essere incentivato ad usarli. Infatti, a detta loro, il traffico eccessivo comporta un rallentamento del mezzo, accumulando ritardo di conseguenza. Specialmente per chi non si può permettere di arrivare a destinazione in ritardo o per chi deve effettuare troppi cambi, si andrà a preferire il mezzo personale, causando così un "loop" che non avrà fine.
Abbiamo inoltre osservato che, per quanto riguarda la questione degli autobus, la domanda non è sempre concerne all'offerta. Entrando più nel dettaglio si può notare come ci siano abbastanza spesso situazioni di questo tipo:
- Pochi autobus ma molto pieni. Alcune persone devono aspettare il prossimo perchè non sono riuscite a salire a causa di ciò
- Molti autobus quasi vuoti. Queste potrebbero essere risorse ricollocabili altrove, dove c'è un reale bisogno

![[2_Soluzione.jpg]]
Il progetto ha come obiettivo la realizzazione di un’applicazione web per aiutare i cittadini a spostarsi nel comune di Trento. Make Your Move consiste infatti nella creazione di tratte per gli autobus a livello dinamico. La tratta verrà decisa la sera prima in base alle segnalazioni raccolte dagli utenti, ovvero Il punto di partenza, quello di arrivo e i relativi orari. Arriverà poi una notifica all'utente su quale sarà il suo bus, dove e quando giungerà

Q&A:
- *Non è confusionario il fatto che delle linee verranno modificate ogni giorno?*
- Make your Move non andrà a modificare tratte già preesistenti, ma verrà creata una linea apposita (nome in codice, "linea D") in modo da generare meno confusione possibile, specialmente tra i nostri utenti più abitudinari :)
- *Se mi dimentico di inserire la tratta per il giorno successivo come faccio ad arrivare a destinazione? Mi tocca per forza usare il mezzo personale?*
- Non necessariamente. Make your Move salva le tratte che l'utente ha considerato come "abitudinarie". In caso il percorso desiderato sia "straordinario" e/o l'utente si è dimenticato di inserirlo, l'applicazione propone (in base a disponibilità e preferenze) mezzi pubblici alternativi come linee autobus tradizionali, monopattini elettrici, biciclette,... Il veicolo personale (inteso come auto o moto) resterà disponibile come ultima spiaggia. In tal caso Make Your Move fornirà un percorso, dove possibile, in zone meno trafficate con simile tempo di arrivo (Eta. max 5 min in più considerando le condizioni di traffico attuali sul tragitto più breve)
- *Sono un utente con disabilità fisiche. L'applicazione può adattarsi alle mie esigenze?*
- Certamente! Make Your Move al momento della registrazione chiederà le preferenze dei veicoli che l'applicazione offre, in modo che sia utenti con bisogni speciali che persone che semplicemente provano un odio profondo verso alcune opzioni, possano personalizzare i loro percorsi con serenità

![[3_Vantaggi.jpg]]
I vantaggi che si otterranno con l'utilizzo della webapp sono molteplici.
Per il comune:
- Miglioramento della viabilità: le zone più soggette a traffico saranno meno congestionate a causa della minor presenza di mezzi personali e di percorsi alternativi suggeriti
- Minor impatto ambientale: sempre a causa di meno auto e moto presenti su strada, l'inquinamento dell'aria sarà in diminuzione
- Costi minori: ottimizzando l'uso dei veicoli pubblici in base alle richieste degli utenti, i costi di mantenimento saranno più contenuti

Per il cittadino:
- Meno disagi: gestendo i veicoli in modo più controllato, è più difficile che i cittadini subiscano disagi per ritardi, affollamenti e congestionamenti
- Ritardi più contenuti: sempre per la minor presenza di veicoli su strada, è più probabile che gli autobus arrivino in orario alle fermate previste (o che comunque, il ritardo difficilmente sia associato al traffico)
## 2. Requisiti Funzionali
### Requisiti funzionali comuni ad Admin e Utente Base
- [ ] RF1: Registrazione: Il sistema deve permettere agli utenti di registrarsi utilizzando mail e un nickname, garantendo così lo pseudo-anonimato (RNF5) e far in modo di tenere traccia di tratte e veicoli preferiti (RF7 e RF10)
- [ ] RF2: Login: Il sistema deve permettere agli utenti di poter accedere col proprio account creato precedentemente (RF1) così da poter accedere ai propri dati salvati e per poter far riconoscere le richieste dei servizi al server
- [ ] RF3: Ricerca: L'utente deve poter effettuare ricerche dei luoghi per indicare il punto di partenza e arrivo
- [ ] RF4: Visualizzazione mappa: L'utente deve essere in grado di visualizzare la mappa interattiva

### Requisiti funzionali Admin
- [ ] RF5: Richieste utenti: Il sistema deve garantire agli admin di visualizzare in blocco le richieste di tratte effettuate dagli utenti (RF7)
- [ ] RF6: Statistiche: Il sistema deve poter permettere agli admin di visualizzare le statistiche riguardanti le richieste e le persone effettivamente salite

### Requisiti funzionali Utente
- [ ] RF7: Richiesta tratta: Il sistema deve permettere all'utente di richiedere il punto di partenza e di arrivo, con i relativi orari
- [ ] RF8: Ricevuta di consegna: Il sistema, una volta che genera la tratta della linea dinamica, deve fornire una risposta all'utente, dichiarando dove e quando si troverà il bus
- [ ] RF9: Proposta di alternativa: Il sistema, se la tratta è satura o la generazione di questa risulta troppo lontana dall'utente, deve fornire un'alternativa valida in base a disponibilità e preferenze (RF10)
- [ ] RF10: Inserimento preferenze: Il sistema deve consentire all'utente di inserire i veicoli preferenziali

## 3. Requisiti Non Funzionali
- [ ] RNF1: Compatibilità: Il sistema deve essere compatibile con i seguenti browser: Chrome (inserisci versione) e Firefox (inserisci versione)
- [ ] RNF2: Performance: Il sistema deve garantire tempi di risposta entro 5 secondi
- [ ] RNF3: Scalabilità: Il sistema deve essere in grado di integrare future espansioni senza difficoltà
- [ ] RNF4: Affidabilità: Il sistema dovrà garantire dei tempi di esecuzione di almeno 15h filate, con un massimo di 2h di "down-time" per manutenzione programmata
- [ ] RNF5: Sicurezza e privacy: Il sistema dovrà garantire uno pseudo-anonimato nella raccolta delle informazioni necessarie (Nickname e mail) 
- [ ] RNF6: Accessibilità: Il sistema deve essere usufruibile da utenti affetti da disabilità
- [ ] RNF7: Lingua: Il sistema sarà in Italiano e in Inglese
- [ ] RNF8: Facilità d'uso: Il sistema, grazie ad un tutorial introduttivo, deve essere facilmente fruibile anche per utenti poco avvezzi all'uso di internet e dello smartphone