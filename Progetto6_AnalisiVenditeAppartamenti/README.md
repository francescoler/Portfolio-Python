Partendo da un file csv con dentro i dati sulla cronologia degli appartamenti si è andati ad indagare 3 possibili richieste:

Analisi delle vendite di appartamenti
Il file "appartamenti.csv" memorizza le informazioni sugli annunci di vendita di appartamenti pubblicati attraverso un sito web.

Nel file sono presenti TRE DIVERSE TIPOLOGIE di righe, il tipo riga è riconoscibile in base alla stringa presente subito dopo tr= come riportato in seguito

tr=inserimento;idAp=0;data=1;m2=50;prezzo=100000

tr=modifica;idAp=0;data=25;prezzo=90000

tr=vendita;idAp=0;data=131

    ...
I valori sono separati da ; e nel file non c'è intestazione (la prima riga contiene già dati). Nel file sono presenti TRE DIVERSE TIPOLOGIE di righe, rispettivamente righe con

tr=inserimento. Questa riga contiene le informazioni su un annuncio di vendita, con queste informazioni: - idAp è un valore numerico che identifica univocamente l'appartamento, - data è la data di pubblicazione dell'annuncio. Una data è un valore intero compreso tra 1 e 365 che rappresenta il giorno dell'anno in cui è avvenuta la pubblicazione. - m2 rappresenta i metri quadrati dell'appartamento - prezzo rappresenta il prezzo, espresso come valore intero, al quale inizialmente è stato messo in vendita l'appartamento
tr=modifica. Questa riga contiene le informazioni su una modifica di prezzo di un appartamento precedentemente messo in vendita. Ogni volta che viene modificato il prezzo di vendita, al file viene aggiunta una riga come questa che riporta il nuovo prezzo di vendita. Le informazioni contenute nella riga sono: - idAp è l'identificatore dell'appartamento a cui è stato cambiato il prezzo - data è la data in cui è avvenuta la modifica. Anche questa data può assumere un valore intero compreso tra 1 e 365 - prezzo è il nuovo prezzo. Un appartamento può subire diverse modifiche di prezzo (o può non subirne).Ogni volta che viene effettuata una modifica, si aggiunge una riga nel file
tr=vendita. Questa riga contiene le informazioni sulla data in cui è stato venduto l'appartamento. Le informazioni contenute nelle righe di questo tipo sono: - idAp è l'identificatore dell'appartamento venduto - data è la data in cui è avvenuta la vendita. Anche qua data può assumere un valore intero compreso tra 1 e 365
Nota bene: per ogni appartamento nel file c'è sicuramente una riga di tipo "inserimento" e una riga di tipo "vendita". Per un appartamento, le righe di "modifica" possono essere assenti o essercene più di una. Le informazioni presenti nel file sono ordinate in base alla data. Quindi le informazioni sull'inserimento, modifica (prezzo) e vendita di uno stesso appartamento possono essere anche distanti tra loro.

PARTE 1 --
Crea una lista di tuple dove ogni tupla contiene i dati di una riga del file.

Esempio:

    [
      ('inserimento', idAp, data, m2, prezzo),
      ('modifica', idAp, data, prezzo),
      ('vendita', idAp, data),
      ...
PARTE 2 --
Crea una lista di tuple avente questa struttura:

[ (idAp, data_pubblicazione, data_vendita, prezzo_iniziale, prezzo_vendita, numero_variazioni), ...]

Ogni tupla riporta informazioni su un appartamento. Il prezzo di vendita di un appartamento è il prezzo riportato nell'ultima modifica (se ci sono state modifiche), oppure il prezzo_iniziale (se non ci sono state modifiche).

L'elemento numero_variazioni rappresenta il numero di variazioni di prezzo, è pari a 0 per gli appartamenti che non hanno subito variazioni di prezzo.

I valori nella tupla devono essere tutti interi.

PARTE 3 --

Crea un dizionario con la seguente struttura:

{ 'aumenti':[idAp1, idAp2, ...], 'diminuzioni':[idAp3, idAp5, ...] }

dove alla chiave 'aumenti' deve essere associata una lista contenente gli identificatori degli appartamenti (idAp) in cui il prezzo di vendita è risultato maggiore del prezzo iniziale (cioè il prezzo al momento della pubblicazione dell'annuncio). Alla chiave 'diminuzioni' deve essere invece associata una lista con gli idAp degli appartamenti in cui il prezzo di vendita è risultato inferiore al prezzo iniziale. Gli appartamenti con prezzo di vendita invariato non devono essere inseriti nella struttura dati
