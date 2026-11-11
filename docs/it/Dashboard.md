# Dashboard

Accedendo alla Movincloud, la homepage “Overview” presenta un riassunto delle quattro aree della piattaforma: inventario, costi, security e monitoring. Vengono mostrate soltanto le aree per cui l’utente ha i permessi.

Sotto il titolo, una barra di collegamenti (“Inventory”, “Costs”, “Security”, “Monitoring”) porta direttamente alla sezione corrispondente della pagina.

La sezione “Key indicators” riassume le quattro aree in altrettante schede: il numero totale delle risorse, il totale dei costi, la percentuale di compliance con il numero di assessment conformi e la media di utilizzo della CPU.

In particolare:

- La sezione “Inventory” mostra un grafico ad anello delle risorse per tipologia, con il totale al centro e, nella legenda, quantità e percentuale di ogni tipologia; sotto, “Resources by provider” riporta una scheda per provider con la distribuzione delle sue risorse e la tipologia più presente.
- La sezione “Costs” mostra il valore ricalcolato del periodo e, per gli utenti che vedono i costi completi, anche il totale, la previsione e la differenza tra ricalcolato e totale; segue il grafico “Cost trend” con i costi giornalieri e cumulati.
- La sezione “Security” mostra un grafico ad anello degli esiti degli assessment (“Compliant”, “Non-compliant”, “Not applicable”) e una scheda con la compliance complessiva in percentuale; sotto, “Assessments by provider” riporta gli esiti provider per provider.
- La sezione “Monitoring” mostra le metriche del tenant selezionato, calcolate come media delle ultime cinque ore: CPU, memoria, storage, pacchetti di rete, vGateway, K8S, bastion e firewall. Le metriche senza campioni nel periodo riportano “No data”. Il pulsante “Show Grafana panels” apre i pannelli Grafana con lo stato operativo, richiudibili con “Hide Grafana panels”.

![Dashboard sezione "Inventory"](assets/images/extract/media/image100.png)

![Dashboard sezione "Monitoring"](assets/images/extract/media/image101.png)

![Dashboard sezione "Costs"](assets/images/extract/media/image102.png)

![Dashboard sezione "Security"](assets/images/extract/media/image103.png)
