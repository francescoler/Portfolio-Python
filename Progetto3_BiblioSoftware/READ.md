- SPECIFICHE DEL PROGETTO

Questo progetto nasce con l'intenzione di creare un software perfettamente funzionante che si possa interfacciare con l'utente in maniera continua per gestire i libri in una biblioteca.

Si è deciso di implementare un menu con cui l'utente possa dialogare e di farlo tramite la creazione di diverse funzioni. Il programma terminerà solo quando l'utente inserirà il comando "esci".

Le funzioni da implementare sono:

aggiungi_libro(titolo, copie)
Descrizione: Aggiunge un nuovo libro alla biblioteca con il numero di copie specificato.
Se il libro esiste già, aggiorna il numero di copie aggiungendo quelle nuove.
Se il libro non esiste, lo aggiunge al sistema.

rimuovi_libro(titolo)
Descrizione: Rimuove un libro dalla biblioteca.
Se il libro esiste, viene eliminato dal sistema.
Se il libro non esiste, il programma stampa un messaggio di errore.

verifica_disponibilita(titolo)
Descrizione: Controlla se un libro è disponibile nella biblioteca.
Restituisce True se almeno una copia è disponibile.
Restituisce False se il libro non esiste o non ci sono copie disponibili.

prendi_in_prestito(titolo)
Descrizione: Riduce il numero di copie disponibili di un libro di 1, simulando un prestito.
Se il libro è disponibile, decrementa il numero di copie di 1.
Se non ci sono copie disponibili o il libro non esiste, stampa un messaggio di errore.

statistiche_biblioteca()
Descrizione: Restituisce un dizionario con informazioni sulla biblioteca.
totale_libri: numero totale di titoli.
copie_totali: numero totale di copie.
media_copie: numero medio di copie per libro.
visualizza_libri()
Descrizione: Mostra un elenco di tutti i libri nella biblioteca insieme al numero di copie disponibili.
Se la biblioteca è vuota, stampa un messaggio che indica che non ci sono libri.

restaurare_libro(titolo, copie)
Descrizione: Ripristina (aggiunge) copie di un libro che è stato preso in prestito o che necessita di più copie.
Se il libro esiste, aggiunge il numero specificato di copie.
Se il libro non esiste, stampa un messaggio di errore.
