RasHome
=======

### About

My home playground


### Version
4.1.0
+ Per sapere quando aprire le finestre nelle sere estive, ogni volta che ricevo la temperatura della camera da letto la confronto con l'ultima temperatura esterna registrata nel database. Quando la temperatura esterna è più bassa di quella interna viene inviato un messaggio telegram per avvisarmi quando spalancare le finestre.
+ Migrato le funzioni di NoRA a SmartNoRA
+ Cambiato il programma per la gestione delle notifiche verso dispositivi Google Home

4.0.1
+ Aggiunto toaster per messaggi del gestore della ricarica auto elettrica
+ Quando viene scelta una carica pecentuale, c'è un ritardo di 2s per aspettare eventuali altre scelte dell'utente prima di inviare la richiesta vera e propria

4.0.0
+ Riscritto gestore di ricarica auto elettrica: Sono stati ragruppati tutte le vecchie funzioni in un unica funzione scritta in javascript. Dovrebbe essere un tentativo di programmazione JS orientata agli oggetti
+ Minime e massime della camera non vengono calcolate ma prelevate dal database influx (ancora da configurare)