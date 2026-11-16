# Sicurezza

La funzionalità di sicurezza di Movincloud mostra lo stato di sicurezza e di conformità delle risorse di inventario presenti sulla piattaforma.

Per accedere alla funzionalità “Sicurezza”, cliccare sull’icona del menu in alto a sinistra: si aprirà la barra del menu, dove occorre selezionare la voce “Sicurezza”. Come mostrato in figura:

![Accesso a Sicurezza](assets/images/extract/media/image268.png)

Il menu della funzionalità comprende la dashboard generale, le dashboard di dettaglio per tipologia di risorsa (macchine virtuali, memoria, dispositivi edge, network e security con i relativi sottotipi), la dashboard “Compliance”, la dashboard “Cloud SIEMs”, la dashboard “Key Vaults”, la dashboard “Cluster” con gli avvisi dei cluster e la dashboard “Confidential Computing”. 

### Dashboard Generale

Entrando nella funzionalità, l’utente si trova nella pagina “Dashboard”, dove vengono mostrati in modo aggregato i dati di sicurezza delle risorse per tutti i provider configurati.

In alto è presente una barra dei filtri che consente di filtrare i risultati per nome policy (“Filtra per nome”), “Sottosistema” e “Stato Risorse” (“Sicuro”, “Insicuro”, “Non applicabile”); i due pulsanti a destra della barra avviano la ricerca e azzerano i filtri. I filtri attivi vengono riepilogati sopra la barra e possono essere rimossi singolarmente.

Sotto i filtri, tre schede riassumono i risultati: lo stato di conformità complessivo (“Sicuro” o “Insicuro”), la conformità generale delle risorse in percentuale con il numero di risorse sicure sul totale e il numero di politiche insicure.

Segue il grafico a barre che indica lo stato di compliance delle risorse assegnate alle policy, suddivise per sottosistema. Passando il mouse su una sezione del grafico, i valori delle schede si aggiornano per mostrare un’anteprima del dettaglio; cliccando su una sezione del grafico vengono applicati automaticamente i filtri “Sottosistema” e “Stato Risorse” alla pagina.

![Dashboard Sicurezza](assets/images/extract/media/image269.png)

Sotto il grafico è presente la tabella delle policy, che viene automaticamente filtrata in base ai filtri selezionati. Per ogni policy sono riportati il nome, la gravità, il sottosistema, l’impatto per l’utente, i rischi, lo stato di conformità e il numero di occorrenze.

Accanto alla tabella, un grafico ad anello riporta la distribuzione delle risorse per stato: le voci della legenda indicano quantità e percentuale di ogni stato e, se cliccate, filtrano la pagina su quello stato. Il pulsante con l’icona del grafico, in alto a destra della tabella, mostra o nasconde la colonna dei grafici per dare più spazio alla tabella.

![Tabella policy](assets/images/extract/media/image270.png)

Cliccando su una riga della tabella si apre una finestra di dettaglio dove è possibile trovare tutte le informazioni relative alla policy selezionata. Nella parte bassa della finestra è disponibile la lista delle risorse coinvolte, con il selettore “Mostra risorse il cui stato è:” per limitarla a uno stato specifico. Accanto a ciascuna risorsa è disponibile un pulsante “link”: una volta cliccato, l’utente verrà reindirizzato alla risorsa di inventario Movincloud in modalità “visualizzazione”.

![Dettaglio policy](assets/images/extract/media/image271.png)

Per uscire dal dettaglio, cliccare sulla “X” in alto a destra della finestra oppure premere “Esc”.

### Dashboard specifiche per tipologia di risorsa

È possibile filtrare ulteriormente le policy per tipologia di risorsa, utilizzando le tab in alto nella pagina.

Una volta selezionata la tipologia di risorsa, è possibile navigare le pagine seguendo le modalità descritte nel paragrafo precedente.

![Dashboard compliance Virtual Machine](assets/images/extract/media/image272.png)

### Dashboard SIEM

Per visualizzare la dashboard SIEM, selezionare la voce “Cloud SIEMs” del menu. In alto è presente la barra dei filtri, dove è possibile selezionare i SIEM di interesse e l’intervallo temporale (“1 Giorno” o “30 Giorni”); i due pulsanti a destra avviano la ricerca e azzerano i filtri. Il pulsante in alto a destra della pagina mette a disposizione la voce “Aggiorna Analytics”, che forza il ricalcolo delle statistiche e segnala con un messaggio l’esito dell’operazione.

Sotto, è presente la sezione “Sommario” che contiene il numero di avvisi, il numero di incidents gravi, il totale degli incidents con l’indicazione di quanti sono nuovi e il numero di eventi totali; sempre all’interno della sezione “Sommario”, se sono presenti incidents, viene mostrato il grafico “Incidents per stato”; seguono i grafici “Alerts per severità” e “Incidents per severità”, cliccabili per filtrare la pagina.

Sotto la sezione “Sommario”, le sezioni “Statistiche” riportano le analisi restituite dal SIEM.

![Dashboard SIEM](assets/images/extract/media/image273.png)

Scorrendo la dashboard SIEM, sono presenti i grafici che indicano le tipologie di evento rilevate nel periodo.

![“Event types" della dashboard SIEM](assets/images/extract/media/image274.png)

Infine, in fondo alla pagina, sono presenti due tabelle: a sinistra la tabella “Alert rules” che mostra un insieme di regole di allarme, mentre a destra la tabella “Incidents” che mostra gli incidenti.

![Tabelle “Alert rules” e “Incidents”](assets/images/extract/media/image275.png)

Cliccando su una riga della tabella si aprirà una finestra di dettaglio, dove è possibile trovare tutte le informazioni relative alla regola o all’incidente selezionato.

![Dettaglio “Incidents”](assets/images/extract/media/image276.png)

### Dashboard Key Vaults

Per visualizzare la dashboard dei Key Vault, selezionare la voce “Key Vaults” del menu. In alto è presente la barra dei filtri, dove è possibile selezionare il vault di interesse; il pulsante in alto a destra della pagina mette a disposizione la voce “Aggiorna Analytics”.

Sotto i filtri, il pannello “Sommario”, richiudibile, riporta il grafico con i totali delle risorse contenute nel vault selezionato.

![Dashboard Key Vault](assets/images/extract/media/image277.png)

Più in basso, le risorse del vault sono organizzate in tab:

- “Secrets”
- “Chiavi”
- “Certificati”
- “Disk Encryption Sets”, presente solo se il vault ne contiene

![Risorse visualizzabili](assets/images/extract/media/image278.png)

Cliccando su una riga della tabella è possibile visualizzare il dettaglio della risorsa selezionata.

![Dettaglio chiave](assets/images/extract/media/image279.png)

### Dashboard Clusters

La voce “Cluster” del menu mostra in modo aggregato tutte le alert generate dai sottosistemi di tipo “Cluster” configurati in Movincloud.

In alto è presente una barra dei filtri che consente di filtrare i risultati per nome (“Filtra Risultati”), “Sottosistema” e “Namespace”; i due pulsanti a destra della barra avviano la ricerca e azzerano i filtri.

Sotto i filtri, tre schede riassuntive riportano la percentuale di avvisi “Info”, “Warning” e “Critici”, con il relativo numero sul totale.

Successivamente, l’utente nota la presenza del grafico a barre che indica il numero totale di “alert” ricevute, suddivise per sottosistema. Passando il mouse su una sezione del grafico, si può notare che i valori visualizzati nella pagina si aggiornano per mostrare un’anteprima del dettaglio. È possibile cliccare su una sezione del grafico per applicare automaticamente il filtro “Sottosistema”.

![Dashboard “Cluster alerts”](assets/images/extract/media/image280.png)

Scorrendo la pagina verso il basso, è presente la tabella “alerts” che verrà automaticamente filtrata in base ai filtri selezionati.

![Tabella alerts](assets/images/extract/media/image281.png)

Cliccando su una riga della tabella si aprirà una finestra di dettaglio, dove è possibile trovare tutte le informazioni relative all’“alert” selezionata.

Per uscire dal dettaglio, cliccare sulla “X” in alto a destra della finestra oppure premere “Esc”.

### Dashboard Compliance

Per visualizzare la dashboard compliance, selezionare la voce “Compliance” del menu.

![Dashboard compliance](assets/images/extract/media/120325001.png)

La pagina è composta da 4 sezioni.
La prima sezione contiene i filtri che permettono la ricerca per nome policy, sottosistema e/o stato di conformità.
La seconda sezione, sempre attiva, contiene le schede riassuntive con i grafici ad anello che indicano lo stato generale delle risorse e dei criteri filtrati, la conformità generale in percentuale e il numero di politiche insicure.

![Sezioni “Filtri” e “grafici a torta”](assets/images/extract/media/120325002.png)

La terza sezione, attiva solo se nei risultati sono presenti più sottosistemi diversi, mostra un grafico a barre, suddiviso per provider, dello stato di compliance delle risorse; anche qui il passaggio del mouse aggiorna le schede e il clic applica il filtro sul sottosistema.
L’ultima sezione contiene una tabella con le informazioni generali sui gruppi di policy: il nome, con l’icona che distingue un policy set da una singola policy, lo stato di conformità e, per risorse e criteri, la percentuale di non conformi con il relativo conteggio.

![Sezioni “grafici a barre” e “tabella”](assets/images/extract/media/120325003.png)

Cliccando su una riga della tabella si apre una modale dove sarà possibile visualizzare l’elenco di tutte le policy configurate nel gruppo, con il relativo conteggio delle risorse; i campi in alto nella modale permettono di filtrare l’elenco per nome e per stato di conformità.
Sempre all’interno della modale, possiamo cliccare su una delle policy visualizzate; così facendo verrà mostrato in basso l’elenco di tutte le macchine assegnate alla policy e il relativo stato.
Accanto a ciascuna risorsa è disponibile un pulsante “link”; una volta cliccato, l’utente verrà reindirizzato alla pagina inventario della risorsa selezionata.

![Dettaglio policy](assets/images/extract/media/120325004.png)

### Dashboard Confidential Computing

Per visualizzare la dashboard del confidential computing, selezionare la voce “Confidential Computing” del menu. La pagina mostra le istanze censite dai server di remote attestation configurati, con l’indicazione dello stato di cifratura della memoria (SEV).

![Dashboard Confidential Computing](assets/images/extract/media/SE001.png)

In alto è presente la barra dei filtri, dove è possibile selezionare la remote attestation di interesse; i due pulsanti a destra avviano la ricerca e azzerano i filtri.

Sotto i filtri, la tabella riporta per ogni istanza la remote attestation di appartenenza, il nome host, il tipo di backend KH e lo stato “Security Encryption Verification”: un lucchetto chiuso verde indica SEV attivo, un lucchetto aperto rosso indica SEV non attivo e un punto interrogativo indica che lo stato non è noto.

Cliccando su una riga della tabella si apre una finestra di dettaglio con le informazioni generali e tecniche dell’istanza (UUID, remote attestation, nome host, tipo di backend KH, stato SEV, SEV Proof, versione del sistema operativo, avvio stimato e data di avvio), le “Backup Locations”, l’ultimo log di sblocco e l’ultimo log SEV.

![Dettaglio Confidential Computing](assets/images/extract/media/SE002.png)

Per uscire dal dettaglio, cliccare sulla “X” in alto a destra della finestra oppure premere “Esc”.
