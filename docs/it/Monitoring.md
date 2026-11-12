# Monitoring

La Movincloud raccoglie metriche da tutti i cloud provider e le aggrega per macro-categorie, così da permettere il confronto tra metriche di provider diversi.

Il modulo di monitoring è accessibile dal menu dedicato, che comprende la dashboard generale, le dashboard di dettaglio per tipologia di risorsa (macchine virtuali, storage, Kubernetes, pod, reti con i relativi sottotipi, bastion e firewall), le quote, gli alert e i report. Come mostrato in figura:

![Accesso al modulo Monitoring](assets/images/extract/media/image259.png)

### Dashboard di monitoring

La voce “Dashboard” mostra una panoramica dell’utilizzo delle risorse, suddivisa per provider e organizzata per tipologia di risorsa associata, mentre le voci di dettaglio limitano la vista a una singola tipologia.

![Dashboard di monitoring](assets/images/extract/media/170325001.png)

#### Filtri della sezione Monitoring

In alto a sinistra sono disponibili i filtri sulle risorse recuperate: tipologia provider, nome del sottosistema e, nelle sole dashboard di dettaglio, nome della risorsa. Permettono la selezione multipla e possono essere combinati per ottenere la granularità desiderata.

![Filtri funzionalità Monitoring](assets/images/extract/media/170325002.png)

### Dashboard Quotas

La pagina “Quotas” mostra i consumi e i limiti applicati ai sottosistemi di tipo VCloud e ai sistemi di backup integrati.

![Accesso alla sezione Quotas](assets/images/extract/media/170325003.png)

In alto è presente la barra dei filtri, che permette di filtrare per provider (“Search by provider”), per sottosistema (“Search by Subsystem”) e per sistema di backup (“Search by Backup System”); i due pulsanti a destra della barra avviano la ricerca e azzerano i filtri.

Sotto i filtri, la tabella riporta per ogni sottosistema il tenant e il nome e, per CPU, memoria, storage e backup, il valore utilizzato, il limite e la percentuale di utilizzo.

![Dashboard Quotas](assets/images/extract/media/170325004.png)

### Allarmi sull’utilizzo delle Quotas

Il modulo “Alerting” invia una notifica quando vengono superate le soglie di utilizzo delle quote. La pagina elenca le regole configurate nel sistema con la schedulazione, il tipo di alert, la modalità di invio, la data di creazione, la data dell’ultimo invio, lo stato della regola (“Enabled” o “Disabled”) e l’esito dell’ultima esecuzione (“In progress”, “Succeeded” o “Failed”).

![Accesso al sistema di Alerting](assets/images/extract/media/090425002.png)

#### Creazione di un nuovo Alert

Il pulsante “New rule”, in alto a destra, apre la pagina di configurazione, organizzata in tre riquadri.

![Creazione nuovo Alert](assets/images/extract/media/090425004.png)

Nel riquadro “Alert configuration”:

- **“Rule active”**: attiva o disattiva la regola
- **“Alert Type”**: selezionare la tipologia di alert
- **“Quota Type”**: selezionare la quota da monitorare, tra CPU, memoria, storage e backup
- **“Threshold (%)”**: inserire la percentuale oltre la quale verrà inviato l’alert
- **“Subsystems”** e **“Backup Systems”**: selezionare i sistemi da monitorare; va indicato almeno uno dei due

Nel riquadro “Schedule configuration” si indicano la frequenza dei controlli, la data e l’ora della prima esecuzione e, se non si seleziona “Do not set end schedule date”, la data e l’ora di fine.

Nel riquadro “Delivery configuration”:

- **“Alert Send Type”**: selezionare la modalità di ricezione dell’alert, via e-mail oppure RabbitMQ (per l’integrazione automatica con altri sistemi)
- **“Alert Format”**: selezionare il formato del file che riporta i dettagli dell’alert. Il campo si abilita dopo aver scelto il tipo di invio: “JSON” è sempre disponibile, “CSV” solo con invio via e-mail
- **“Emails”**: presente solo con invio via e-mail. Dopo aver inserito un indirizzo è necessario premere “Invio” sulla tastiera per confermarlo: l’indirizzo passa nel box sottostante e il campo viene svuotato per permettere l’inserimento di un nuovo indirizzo, se necessario.

![Pagina di configurazione](assets/images/extract/media/090425005.png)

#### Visualizzazione, modifica e cancellazione di un Alert

Per ogni regola, il pulsante “tre puntini” a destra mette a disposizione le seguenti operazioni:

- “Show rule” per visualizzare la configurazione della regola
- “Edit rule” per modificarne le impostazioni
- “Delete rule” per eliminarla e interrompere l’invio delle notifiche
- “Enable rule” e “Disable rule” per sospendere o riattivare i controlli senza eliminare la regola
- “Schedule Now” per eseguire subito un controllo
- “Schedule history” per consultare lo storico delle esecuzioni

![Operazioni sugli alert](assets/images/extract/media/090425003.png)

### Strumenti di reportistica

La funzionalità di reportistica, specifica per funzionalità, consente di generare report globali delle informazioni disponibili per i vari provider; all’interno delle pagine è anche possibile creare dei file per facilitare la condivisione delle informazioni.

Per accedere alla funzionalità, selezionare la voce “Reports” del menu di Monitoring.

![Accesso alla reportistica](assets/images/extract/media/MR001.png)

#### Tipologie di report disponibili

- **Monitoring Threshold Quotas** – Elenco dei sottosistemi VCloud e/o Backup integrati nella Movincloud, con dettaglio delle quote di utilizzo (CPU, Memoria, Storage, Backup). In base alla combinazione di filtri selezionata, è possibile filtrare i sottosistemi che superano una certa soglia di utilizzo.

#### Creazione di un report

In alto a destra della pagina, il pulsante “New report” avvia la creazione di un report: viene visualizzata una modale con l’elenco delle tipologie disponibili.

![Creazione nuovo Report](assets/images/extract/media/MR002.png)

Una volta selezionata la tipologia, cliccare su “Configure” per impostare i filtri del report. I campi richiesti nella sezione “Report data” dipendono dalla tipologia: per il Monitoring Threshold Quotas sono il provider, il sottosistema, il sistema di backup e la soglia di utilizzo. Se la tipologia prevede un intervallo di date, il campo “Date range” compare nella stessa sezione per i soli report one-shot.

![Configurazione report](assets/images/extract/media/MR003.png)

A questo punto l’utente può scegliere tra due azioni diverse:

- creare un report statico che verrà salvato nel sistema;
- pianificare una schedulazione che generi il report periodicamente.

Per confermare la creazione di un report statico, verificare che per il campo “Report Type” sia selezionato “One-Shot” e cliccare sul pulsante “Submit” in basso. Dopo un periodo di caricamento il report generato sarà visibile nell’elenco del tab “Ready”.

![Elenco report generati](assets/images/extract/media/MR004.png)

##### Pianificazione report

Se invece si desidera l’esecuzione automatica del report, selezionare “Recurring” per il campo “Report Type”: la finestra si aggiorna mostrando i parametri aggiuntivi del report periodico.

I parametri da inserire sono:

- “Period”: la frequenza di invio del report (oraria, giornaliera, ...); scegliendo “Custom” è possibile inserire direttamente un’espressione Cron, che viene validata dal sistema
- data e ora della prima schedulazione, con la possibilità di inviare subito la prima occorrenza (“First schedule now”)
- data e ora di fine schedulazione, oppure l’opzione “Do not set end schedule date” per non impostarla
- “Receive only if not empty”: se selezionato, il file non verrà inviato quando non contiene informazioni
- “Report's language”: la lingua utilizzata nel report
- “File format”: uno o più formati di file da includere nella mail
- “User E-mails”: gli indirizzi a cui inviare i report. Dopo aver inserito un indirizzo è necessario premere “Invio” sulla tastiera per confermarlo: l’indirizzo passa nel box sottostante e il campo viene svuotato per permettere l’inserimento di un nuovo indirizzo, se necessario

![Parametri report pianificato](assets/images/extract/media/MR005.png)

Configurati tutti i parametri, il pulsante “Submit” diventa cliccabile: cliccarlo per confermare l’inserimento e, dopo un periodo di caricamento, la schedulazione sarà visibile nell’elenco.

##### Elenco report pianificati

Per visualizzare l’elenco dei report pianificati, selezionare il tab “Scheduled” in alto nella pagina dei report.

![Elenco report pianificati](assets/images/extract/media/MR006.png)

In questa pagina troviamo l’elenco e le relative informazioni dei report pianificati presenti nel sistema. Per ogni risultato, cliccando sul pulsante “tre puntini” a destra, sarà possibile:

- visualizzare l’ultimo report generato (“Show report”)
- modificare le impostazioni della schedulazione (“Edit”), senza poter cambiare i provider o i sottosistemi selezionati
- eliminare la schedulazione (“Remove”) per interrompere l’invio delle e-mail
- sospendere o riattivare l’invio delle e-mail (“Disable schedule” ed “Enable schedule”)

![Modifica schedulazione](assets/images/extract/media/MR007.png)

##### Utilizzo dei report

Cliccando sulla riga di un report statico, o utilizzando il pulsante “Show report” disponibile per i report pianificati, si apre la pagina di dettaglio del report selezionato.

In alto sono riportati i filtri utilizzati per generare il report e l’intervallo di date dei dati; a destra sono presenti i pulsanti “PRINT” ed “EXPORT”. Sotto è presente la tabella riassuntiva, paginata; se il report contiene troppe righe per essere visualizzato interamente a schermo, un avviso invita a scaricare il file per consultarlo per intero.

Cliccando su “PRINT” si apre la finestra di stampa del browser, con l’anteprima del report. Cliccando su “EXPORT” è possibile esportare il report in formato “.csv”, “.json” o “.pdf”.

Per tornare alla lista dei report, cliccare sul pulsante “CLOSE” in basso a destra oppure sulla freccia verso sinistra in alto, accanto al titolo del report.

![Dettaglio report](assets/images/extract/media/image148.png)
