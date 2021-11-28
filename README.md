RasHome
=======
# Il progetto
### About
Questo è un mio progetto hobbistico iniziato 3 anni fa quando mi sono tranciato un dito mentre lavoravo sulla mia auto (mozzarsi le dita non è un passaggio obbligatorio per far funzionare il progetto).
Inizialmente era solo un esperimento per visualizzare qualche valore spedito da due ESP8266 su MQTT, e alla fine è diventato il mio centro di controllo di casa.
## Struttura progetto
# Software
Il cuore del programma gira su un istanza di NodeRed su un Raspberry PI 3 (adesso migrato su un minipc di riciclo con Ubuntu Server perchè il raspberry iniziava a faticare) che acquisisce le telemetrie dei sensori tramite un broker MQTT (*Mosquitto*) installato sullo stesso.
I sensori si appoggiano al fantastico progetto [NoRA](https://github.com/andrei-tatar/node-red-contrib-nora). Tette le luci e sensori possono essere interfacciate con il proprio assistente Google, solo che il progetto iniziale è arrivato al limite si sopportazione e di fatto i miei dispositivi non sono più usabili tramite Google. L'autore sta lavorando ad una versione a pagamento (SmartNoRA) che sopporterà più traffico.
# Database
I dati acquisiti vengono salvati su database InfluxDB e visualizzabili con Chronograf (Ho installato tutto lo stack TICK ma Kapacitor e Telegraf al momento non li uso)

# Hardware
Dividendo per stanza:
* Soggiorno
Un ESP8266 con un DHT11 e una fotoresistenza per monitorare i dati ambientali della stanza
Un ESP8266 (rimosso per problemi al mio impianto) con un relè per la luce
* Cucina
Un Sonoff MINI che comanda una ventola che spinge l'aria calda dalla stufa in cucina direttamente in camera al piano di sopra
* Scale
Un Sonoff BASIC per la luce
* Server Room
Un ESP8266 con un DHT11 e una fotoresistenza per monitorare i dati ambientali della stanza
* Camera
Un ESP8266 con un DHT11 e una fotoresistenza per monitorare i dati ambientali della stanza
* Soffitta
Un ESP8266 con un DHT11 e una fotoresistenza per monitorare i dati ambientali della stanza
* Cortile
Un NodeMCU con un BMP280 per monitorare i dati ambientali
Un ESP8266 con un relè per la luce
Un Sonoff POW2 per monitorare e controllare la ricarica della mia auto elettrica
Un Sonoff POW2 per monitorare l'energia prodotta da due panellini solari che immettono direttamente in rete.

# Pics
![Sinottico](https://github.com/metalneo-glitch/RasHome/blob/master/img/Sinottico.png)
![Controllo dispositivi](https://github.com/metalneo-glitch/RasHome/blob/master/img/Dispositivi.png)
![Monitoraggio Energia](https://github.com/metalneo-glitch/RasHome/blob/master/img/Energia.png)
![Monitoraggio Rete](https://github.com/metalneo-glitch/RasHome/blob/master/img/Network.png)
![Ricarica EV](https://github.com/metalneo-glitch/RasHome/blob/master/img/Ricarica_EV.png)
![Speedtest Rete](https://github.com/metalneo-glitch/RasHome/blob/master/img/Speedtest.png)
![Info](https://github.com/metalneo-glitch/RasHome/blob/master/img/About.png)
### Version
<<<<<<< HEAD
4.1.0
+ Per sapere quando aprire le finestre nelle sere estive, ogni volta che ricevo la temperatura della camera da letto la confronto con l'ultima temperatura esterna registrata nel database. Quando la temperatura esterna è più bassa di quella interna viene inviato un messaggio telegram per avvisarmi quando spalancare le finestre.
+ Cambiato il programma per la gestione delle notifiche verso dispositivi Google Home
=======
4.0.2
+ Valori min/max visualizzati nel sinottico sono prelevati tramite una query a InfluxDB
+ Quando viene scelta una carica pecentuale, c'è un ritardo di 2s per aspettare eventuali altre scelte dell'utente prima di inviare la richiesta vera e propria

4.0.0
+ Riscritto gestore di ricarica auto elettrica: Sono stati ragruppati tutte le vecchie funzioni in un unica funzione scritta in javascript. Dovrebbe essere un tentativo di programmazione JS orientata agli oggetti
+ Minime e massime della camera non vengono calcolate ma prelevate dal database influx (ancora da configurare)
