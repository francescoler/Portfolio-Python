- SPECIFICHE DEL PROGETTO -

In questo progetto partendo da un file CSV si è andati ad indagare ed analizzare in maniera simulata alcune aspetti relativi agli addebiti delle bollette telefoniche, seguendo le specifiche di seguito riportate utilizzando 3 funzioni:

Il file “telefonate.csv” contiene informazioni sulle telefonate effettuate in un mese da alcuni clienti di un operatore di telefonia cellulare.

La prima riga contiene l'intestazione delle colonne. Ogni riga riporta le
   informazioni seguenti.

   * Cod_Chiamante: un intero che identifica univocamente il
     cliente che ha effettuato la chiamata
   * Cod_Destinatario: un intero che identifica univocamente il
     cliente che ha ricevuto la chiamata
   * Cod_Cella_Chiamante: un intero che identifica l'area nella
     quale si trova il cliente che ha effettuato la chiamata
   * Cod_Cella_Destinatario: un intero che identifica l'area nella
     quale si trova il cliente che ha ricevuto la chiamata
   * GGI:HHI:MMI rappresentano rispettivamente il giorno, l'ora
     e il minuto in cui e' iniziata la chiamata
   * GGF:HHF:MMF rappresentano rispettivamente il giorno, l'ora
     e il minuto in cui e' finita la chiamata
     - sia GGI sia GGF contengono valore interi (compresi tra 1 e 31) che rappresentano il giorno del mese
     - sia HHI sia HHF contengono valori interi (compresi tra 0 e 23) che rappresentano un'ora del giorno
     - sia MMI sia MMF contengono valori interi (compresi tra 0 e 59) che rappresentano un minuto di un'ora

All'interno del file sono presenti righe che iniziano con il  carattere ''#”, inserite per indicare il malfunzionamento delle celle.

La prima funzione che dovrai implementare è la funzione ottieniDatiTelefonate(nomeFile) 

La funzione accetta come unico parametro in ingresso il nome del file con i dati sulle telefonate effettuate. 
Nota bene: il nome del file da aprire e' passato alla funzione come parametro. La funzione dovra' restituire una lista formata da tuple, dove ogni tupla contiene i seguenti dati (ogni tupla corrisponde ad una telefonata):
   (Cod_Chiamante, Cod_Destinatario, Cod_Cella_Chiamante, Cod_Cella_Destinatario, Numeo_Minuti_Di_Conversazione ).
I minuti di conversazione si calcolano includendo anche il minuto di inizio della conversazione, per esempio una telefonata iniziata alle (GGI;HHI;MMI) 10;14;30 e terminata alle (GGF;HHF;MMF) 10;14;34 dura 5 minuti (34-30+1=5).
Nella tupla, i dati dovranno essere memorizzati sotto forma di valori interi.
Ci sono alcune righe del file che contengono dati sbagliati, nella lista restituita non dovranno essere presenti le tuple corrispondenti alle righe con dati sbagliati.

Le righe che rispettano i criteri indicati qua di seguito sono da considerarsi corrette:
   * Cod_Chiamante e Cod_Destinatario devono essere diversi (non sono ammesse
     chiamate a se stessi)
   * GGI, HHI, MMI devono appartenere ai rispettivi insiemi di valori come da
     specifiche precedenti.
   * L'inizio della chiamata non puo' essere successivo alla fine della chiamata.
     - (GGI:HHI:MMI) 10:14:30 , (GGF:HHF:MMF) 10:14:34  Questa va bene
     - (GGI:HHI:MMI) 21:10:10 , (GGF:HHF:MMF) 21:10:10  Questa va bene (la telefonata dura un minuto)
     - (GGI:HHI:MMI) 30:20:40 , (GGF:HHF:MMF) 30:20:30  Da eliminare
   * Telefonate piu' lunghe di 10 ore sono da considerarsi errori

 Per il calcolo dei minuti di conversazione, si suggerisce di trasformare (data,ora,minuto) in un intero corrispondente al numero di minuti trascorsi dall'inizio del mese. Siete invitati a creare delle funzioni accessorie per svolgere le operazioni
che si ripetono più volte all'interno del codice.


 - calcolaBollette(datiChiamate). La funzione accetta come parametro in ingresso la struttura dati restituita dalla funzione precedente.  La funzione dovra' restituire un dizionario di coppie chiave valore  in cui la chiave e' il codice del cliente e il valore e' un float corrispondente all'importo che il cliente deve pagare per le chiamate effettuate nel mese. La tariffazione delle chiamate avviene sulla base dei minuti di conversazione, un cliente paga 0.10 euro (10 centesimi di euro) per ogni minuto di chiamata effettuata. Il cliente che riceve la chiamata non paga niente.
Ogni cliente ha un bonus di 20 minuti gratuiti al mese, quindi il cliente paghera' solamente per i minuti eccedenti il bonus. Per esempio se il cliente 1 effettua chiamate per 55 minuti e il cliente 2 effettua chiamate per 15 minuti, il dizionario restituito dovra' contenere: {1:3.5, 2:0}. Il cliente 1 ha 35 minuti eccedenti il bonus tariffati a 0.10
centesimi l'uno. L'insieme dei clienti contenuti nel dizionario e' formato da quei clienti che appaiono almeno una volta come chiamanti nella struttura dati fornita in ingresso.

calcolaCelleCongestionate(datiChiamate).  La funzione accetta come parametro in ingresso la struttura dati creata dalla funzione ottieniDatiTelefonate. La funzione deve identificare le celle (cioe' le aree) che hanno un elevato carico di telefonate. Per far cio', dovete calcolare il totale delle telefonate fatte da una cella. Considerate solo le telefonate in partenza da una cella, non le chiamate ricevute. Poi, dovete fare la media. Sono da considerarsi congestionate le celle nelle quali il numero di telefonate effettuate e' maggiore alla media.La funzione dovra' restituire una lista con i codici delle celle congestionate.
