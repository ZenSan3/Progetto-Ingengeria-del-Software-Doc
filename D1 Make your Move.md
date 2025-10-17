
## Dipartimento di Ingegneria e Scienza dell’Informazione

| **Progetto:**             | **Make your Move**          |
| ------------------------- | --------------------------- |
| **Titolo del documento:** | **Descrizione di Progetto** |
 
**Document Info**

| Doc. Nam        | D1-DescrizioneProgetto                                                                 |
| :-------------- | :------------------------------------------------------------------------------------- |
| **Description** | Documento di analisi dei requisiti funzionali, non funzionali, user story e front-end. |
| **Doc. Number** | D1 V0.2                                                                                |

## Indice

1. Il progetto Make your Move
2. Requisiti Funzionali
3. Requisiti Non Funzionali

## 1\. Il progetto Make your Move

![[1_Problematiche.jpg]]

Il problema che abbiamo identificato è legato alla viabilità di Trento. Infatti non è raro trovare tanto traffico per le strade, in alcuni casi tratte per cui basterebbero 15 minuti si trasformano in 30 min o anche 40 min. Inoltre i bus ci sono però sono a volte troppo pieni o troppo vuoti. Per chi inoltre ha forti abitudini e non ha un modo per spostarsi velocemente come biciclette, monopattini o veicoli a motore devono a volte fare due o più cambi di autobus. \[Continuare\]

![[2_Soluzione.jpg]]
Il progetto ha come obiettivo la realizzazione di un’applicazione web (telefono?) per aiutare i cittadini a spostarsi nel comune di Trento. La prima parte consiste nella creazione di tragitti per gli autobus (linee apposite) dinamiche. La tratta verrà decisa la sera prima in base alle segnalazioni degli utenti. Per esempio si potrà decidere di partire dalla stazione A alla stazione B. Se invece l’utente o si è dimenticato oppure è impossibilitato ad usare i mezzi pubblici potrà selezionare un veicolo preferito come biciclette o monopattini e verranno consigliate le stazioni più vicine ai punti A e B selezionati e del veicolo selezionato.

![[3_Vantaggi.jpg]]
Vantaggi per il Comune:
* Miglioramento della viabilità: il traffico diminuirà e di conseguenza avendo meno automobili per le strade linquinamento calerà a sua volta  
* Minori costi: Potendo così ottimizzare i veicoli ci saranno meno costi di mantenimento sia di veicoli poco usati sia di bus poco affollati.


Vantaggi per il Cittadino:
* Meno disagi: Gestendo i veicoli in modo più controllato è più difficile subire ritardi e disagi nel non riuscire ad usufruire del servizio di mobilità per affollamento.  
* Puntualità: Diminuendo le automobili si crea sempre meno traffico e quindi è più facile arrivare da punto A a punto B senza rimanere fermi nel traffico

## 2. Requisiti Funzionali

### Requisiti funzionali Comuni ad Admin e Utente Base
- [ ] Registrazione: Il sistema deve permettere agli utenti di registrarsi così da tenere traccia di: 
	- Tratte preferite
	- Veicolo preferito
	- Impossibilità ad usare un veicolo
- [ ] Login: Il sistema deve permettere agli utenti di poter fare login così da poter accedere ai propri dati salvati e per poter far riconoscere le richieste dei servizi al server
- [ ] Ricerca: Gli utenti devono poter ricercare le fermate oppure le stazioni dell'erogazione dei veicoli
- [ ] Visualizzazione mappa: Il sistema deve consentire a qualsiasi utente di visualizzare la mappa

### Requisiti funzionali Admin
- [ ] Accesso alle richieste
- [ ] Accesso alle statistiche

### Requisiti funzionali Utente
- [ ] Richiedere la Tratta
- [ ] Ricevere la conferma o l'alternativa
- [ ] Inserire le proprie preferenze o Impossibilità

## 3. Requisiti Non Funzionali
- [ ] Compatibilità: Chrome e Firefox
- [ ] Performance: risposta entro 3 sec
- [ ] Scalabilità
- [ ] Affidabilità
- [ ] Sicurezza
- [ ] Accessibilità
- [ ] Lingua
- [ ] Facilità d'uso