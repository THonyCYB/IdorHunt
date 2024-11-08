IdorHunt - Scansione vulnerabilità IDOR

IdorHunt è uno strumento per la scansione automatica delle vulnerabilità di Insecure Direct Object References (IDOR) nelle applicazioni web. Consente di testare vari parametri nelle URL per rilevare vulnerabilità di accesso non autorizzato ai dati, aiutando gli sviluppatori e i pentester a identificare possibili falle di sicurezza.
Caratteristiche

    Test automatico per rilevare vulnerabilità IDOR in applicazioni web.
    Supporta parametri personalizzabili da testare.
    Output dettagliato in un file di report.
    Facile da usare da linea di comando.

Requisiti

    Python 3.x
    Libreria requests: utilizzata per inviare le richieste HTTP.

Per installare la libreria necessaria, esegui il seguente comando:

pip install requests

Installazione

    Clona il repository:

    Esegui il seguente comando per clonare il progetto:

git clone https://github.com/THonyCYB/IdorHunt.git

Naviga nella cartella del progetto:

cd IdorHunt

(Facoltativo) Crea un ambiente virtuale:

È una buona pratica utilizzare un ambiente virtuale per evitare conflitti di dipendenze.

    Per Linux/Mac:

python3 -m venv venv
source venv/bin/activate

Per Windows:

    python -m venv venv
    venv\Scripts\activate

Installa le dipendenze:

Installa la libreria requests:

    pip install requests

Uso

Per eseguire IdorHunt, utilizza il comando seguente nel terminale:

python IdorHunt.py -u <URL> -p <valori>

Opzioni

    -u <URL>: URL dell'applicazione web da testare (es. http://example.com/resource?id=1).
        Esempio: -u http://example.com/resource?id=1

    -p <valori>: Lista di valori da testare per i parametri (es. 1,2,3,4,5).
        Esempio: -p 1,2,3,4,5

    -t <timeout>: Tempo di timeout per ogni richiesta in secondi. Il valore predefinito è 5.
        Esempio: -t 10

    -r <file>: Nome del file di report per salvare i risultati. Se non fornito, il nome del file sarà generato automaticamente con la data e l'ora.
        Esempio: -r report_idor.txt

    -v: Abilita la modalità verbose per vedere un'output più dettagliato delle richieste HTTP.

    -h: Mostra il messaggio di aiuto.

Esempi di utilizzo:

    Scansione base:

python IdorHunt.py -u http://example.com/resource?id=1 -p 1,2,3,4,5

Scansione con timeout di 10 secondi e report personalizzato:

python IdorHunt.py -u http://example.com/resource?id=1 -p 1,2,3,4,5 -t 10 -r idor_report.txt

Scansione in modalità verbose:

    python IdorHunt.py -u http://example.com/resource?id=1 -p 1,2,3,4,5 -v

Descrizione del Funzionamento

    Test delle vulnerabilità: Lo script invia richieste HTTP all'URL specificato, testando vari valori per i parametri indicati.
    Rilevamento delle vulnerabilità IDOR: Se la risposta è un HTTP 200 OK per un URL che dovrebbe essere privato, ciò potrebbe indicare una vulnerabilità di tipo IDOR.
    Output: I risultati vengono scritti in un file di report che descrive ciascun URL testato, insieme allo status della risposta HTTP (200, 403, 404, 500, ecc.).

Contribuire

Se vuoi contribuire al progetto IdorHunt, sentiti libero di fare un fork del repository, apportare modifiche e inviare una pull request. Segui questi passaggi per contribuire:

    Forka il repository.
    Crea una nuova branch (git checkout -b feature/nome-feature).
    Aggiungi le tue modifiche.
    Fai il commit delle tue modifiche (git commit -m 'Aggiunta feature').
    Invia una pull request.

Licenza

Questo progetto è rilasciato sotto la Licenza MIT. Puoi consultare il file LICENSE per maggiori dettagli.
Aggiunta del file requirements.txt

Se desideri usare il file requirements.txt per gestire le dipendenze, puoi crearlo con il seguente contenuto:

requests==2.28.1

