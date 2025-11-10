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