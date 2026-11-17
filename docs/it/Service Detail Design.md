# Service Detail Design

Il servizio Service Detail Design è la soluzione implementata per la gestione delle richieste, che devono poi essere lavorate all’interno del nostro ambiente da un utente autorizzato.

Per accedere a Service Detail Design, effettuare il login su Movincloud con l’utente Service Manager, poi cliccare sull’icona del menu in alto a sinistra e selezionare la voce “Service Detail Design”. Come mostrato in figura:

![Accesso al modulo Service Detail Design](assets/images/extract/media/image339.png)

Verrà mostrata la pagina “Ordini di Lavoro”, dove è possibile filtrare i work order già creati. In alto è presente la barra dei filtri:

- “Seleziona Stato…”, che permette di selezionare più stati contemporaneamente (“Nuovo”, “In corso”, “In pausa”, “Completato”, “Rifiutato”); la voce “Seleziona Tutti” in testa all’elenco attiva o disattiva tutti gli stati in un colpo;
- “Seleziona Cliente…”;
- “Seleziona un Tipo di Servizio…”;
- il periodo di creazione (“Ultimi 30 giorni”, “Ultimi 90 giorni”, “Anno precedente”, “Anno attuale”, “Data Personalizzata”);
- l’intervallo di date, che mostra le date del periodo scelto ed è modificabile solo selezionando “Data Personalizzata”.

La tabella mostra le informazioni generali del Work Order.

![Filtri funzionalità Service Detail Design](assets/images/extract/media/image340.png)

Cliccare su una riga di work order, in un punto qualsiasi tranne la colonna “Azioni”, per visualizzarne il contenuto; si aprirà la finestra “Dettagli Ordine di Lavoro”, con le informazioni generali in alto e le altre sezioni raccolte in pannelli che si espandono cliccandoci sopra. I pannelli “Referenti” e “Parametri” compaiono solo se la richiesta li contiene, mentre “Esito Lavorazione” compare solo per gli ordini completati.

Per uscire dalla visualizzazione di dettaglio, cliccare sulla “X” in alto a destra della finestra oppure premere “Esc”.

![Dettaglio Work Order](assets/images/extract/media/image341.png)

### Flusso Work Order

Per prendere in carico un work order, cliccare sul pulsante “Riprendi ordine”, il simbolo “Play” accanto a un ordine in stato “Nuovo” o “In pausa”.

Verrà visualizzata una notifica di cambio stato a schermo e lo stato corrente dell’Ordine diventa “In corso”; i pulsanti dell’ordine corrispondente vengono modificati:

- cliccando il pulsante “Metti in pausa”, l’ordine passerà in stato “In pausa”;
- cliccando il pulsante “Marca come completato”, è possibile chiudere il Work Order; il pulsante resta visibile fino alla chiusura dell’ordine, ma è utilizzabile solo mentre l’ordine è “In corso”.

Un ordine già preso in carico può essere lavorato solo dall’operatore che lo ha in carico: agli altri utenti i pulsanti dell’ordine appaiono disattivati.

![Pagina gestione work order Service Detail Design](assets/images/extract/media/image342.png)

Quando viene cliccato il pulsante “Marca come completato”, viene visualizzata a schermo la finestra “Chiudi Ordine”, dove è possibile inserire le informazioni da allegare all’ordine, nello specifico:

- l’esito della lavorazione, obbligatorio;
- una descrizione dell’esito scelto.

![Chiusura Work order](assets/images/extract/media/image343.png)

Scorrendo la finestra verso il basso, troviamo la sezione “Dati di Consegna”.

Nella riga in fondo è possibile inserire ulteriori parametri come coppie chiave/valore, dopo cliccare il pulsante “Plus” per confermare l’inserimento; per eliminare una coppia aggiunta, cliccare il pulsante “Minus”.

Una volta inseriti tutti i parametri, cliccare il pulsante “Fine”: l’ordine passa in stato “Completato”.

![Inserimento parametri](assets/images/extract/media/image344.png)

Dopo aver completato l’ordine, è possibile riaprire il dettaglio e visualizzare le informazioni inserite durante la lavorazione.

![Informazioni aggiunte durante la lavorazione](assets/images/extract/media/image345.png)
