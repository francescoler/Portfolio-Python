L'azienda F1 Analytics è specializzata nell'analisi delle prestazioni dei piloti e dei team nel mondo della Formula 1.
L'obiettivo di questo progetto è analizzare i risultati del Campionato Mondiale di Formula 1 della stagione 2008, utilizzando i dati contenuti nel file formula1_data.csv.

Questo file contiene informazioni dettagliate sui piloti, i costruttori, le città e i paesi dei Gran Premi, nonché l'ordine di arrivo di ogni pilota.
Basandosi su questi dati, verranno implementate diverse funzioni per fornire un'analisi approfondita dei punti, delle vittorie e dei podi sia a livello individuale che di costruttori.

Dataset Il dataset formula1_data.csv contiene le seguenti colonne:

Driver: Nome del pilota.
Team: Nome del costruttore per il quale il pilota gareggia.
Race: Città in cui si è svolto il Gran Premio.
Country: Paese in cui si è svolto il Gran Premio.
Position: Numero compreso tra 0 e 8 che indica l'ordine di arrivo del pilota (0 significa che il pilota non è arrivato tra i primi 8 e non ha ottenuto punti).
Al termine di ogni Gran Premio, i punti vengono assegnati ai piloti in base al loro ordine di arrivo come segue:
- 1° posto: 10 punti - 2° posto: 8 punti - 3° posto: 6 punti - 4° posto: 5 punti - 5° posto: 4 punti - 6° posto: 3 punti - 7° posto: 2 punti - 8° posto: 1 punto - 9° posto o oltre: 0 punti
