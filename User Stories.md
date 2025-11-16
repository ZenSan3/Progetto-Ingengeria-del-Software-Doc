1. US1: registrazione credenziali (RF1)
2. US2: login (RF2)
3. US3: ricerca (RF3)
4. US4: visualizzazione mappa (RF4)
5. US5: richieste utenti (RF5)
6. US6: statistiche (RF6)
7. US7: richiesta tratta (RF7)
8. US8: ricevuta di consegna (RF8)
9. US9: proposta di alternativa (RF9)
10. US10: preferenze (RF10)
11. US11: modifiche (RF11)
12. US12: gestione utenti (RF12)
13. US13: disabilità (RF7)
14. US14: ricerca con filtri (RF3)
15. US15: tratta predefinita/salvata (RF7)
16. US16: richiesta tratta (da 2 a 9 persone) (RF7)
17. US17: richiesta tratta (da 10 persone in poi) (RF7)
## 5. User Story
### User Story 1 - Associata allo Use Case RF1: Registrazione
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