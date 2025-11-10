# Login e Autenticazione
## Cose necessarie per il login:
- Username
- Mail
- Password
- Check disabilità
	- Motoria lieve (stampelle/protesi)
	- Motoria  pesante (Carrozzina)
	- Cognitiva (sociale)
	- Sensoriale (cecità, sordità)
	- ? flag disabilità temporanee (gesso, carrozzina entrambe le gambe ingessate)

## Tipi di utenti:
- Utente anonimo: Istanza temporanea in cui l'utente deve ancora fare login o autenticazione. In questo stato l'utilizzatore può vedere i mezzi e le tratte ma non può impostare le preferenze e non può fare richiesta per le tratte del giorno dopo.
- Utente base: utilizza le funzioni necessarie (principio di Parnas) per usufruire dell'applicazione. Quindi può vedere quello che vede l'utente anomalo ma può sia prenotare le tratte del giorno dopo che impostare le preferenze.
- Operatore: E' esclusivo del comune e delle aziende che mettono a disposizione i servizi (terze parti). Può vedere e accettare le richieste, vedere i dati per le statistiche e dare annunci (lavori, fermate sospese, tratte dei bus finali), però non può fare modifiche a impostazioni e accedere ai dati dell'utente
- Admin: Può fare modifiche all'applicazione e provare funzionalità "in prova" oltre che bannare utenti che usano in modo dannoso l'applicazione (es false richieste per allungare la tratta)

## Use Case
### Use Case RF1: Registrazione
#### Riassunto:
Questo Use case descrive come l'utente anonimo può registrare un nuovo account a cui poi potrà fare login.
#### Descrizione
1. L'utente parte come anonimo e per registrarsi deve cliccare sull'apposito bottone.
2. Nella schermata di registrazione c'è un form i cui campi obbligatori sono: Username, Mail, Password. Mentre i campi opzionali sono: Check disabilità e tipo utente
3. Viene mandata una mail con un link per la conferma della registrazione.
4. Cliccando sul link la registrazione viene finalizzata e salvata.
#### Eccezioni
1. Se l'utente non inserisce i campi obbligatori la mail non verrà inviata e la registrazione non potrà proseguire.
2. Se l'utente non usa il link l'utente non viene finalizzato e aggiunto al database.
#### Estensioni
Se il tipo dell'utente è operatore o admin prima che la mail di conferma venga inviata chiede l'autorizzazione a un admin per controllare che sia legittimo.