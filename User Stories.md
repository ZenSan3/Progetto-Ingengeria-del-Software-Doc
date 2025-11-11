## 5. User Story
### User Story 1 - Associata allo Use Case RF1:  Registrazione
#### Scelta tra credenziali locali o autenticazione tramite google
Come qualsiasi tipo di utente, voglio decidere personalmente se quando voglio creare l'account usare credenziali locali oppure se usare il sistema di autenticazione di Google in modo da scegliere quello che preferisco
#### Criteri di accettazione
- Tutti i tipi di utente possono scegliere tra la registrazione con Google o in locale
- Dopo una registrazione riuscita viene inviata la mail e si viene reindirizzati alla schermata di login
- Se avviene una registrazione errata (es. caratteri non ammessi o account google non esistente) devono apparire messaggi di errore adeguati.

#### TASKS - User Story 1
1. Integrare entrambe le opzioni di registrazione(locale, Google)
2. Configurare il flusso decisionale della registrazione
3. Gestire le azioni da fare dopo che la registrazione va a buon fine
4. Testare che entrambe le registrazioni vadano a buon fine
5. Implementare i messaggi di errore per ogni metodo