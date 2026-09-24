# Bagno Marè — prima versione del sito

Sito in italiano, responsive, basato sulle foto e sulla palette fornite. Include la pagina pubblica, il modulo prenotazioni e un’area riservata per la gestione.

## Avvio in locale

Serve Python 3.9 o superiore. Nel terminale PowerShell, dalla cartella `mare-site`, imposta le credenziali iniziali e avvia il server:

```powershell
$env:MARE_ADMIN_USER = "gestore"
$env:MARE_ADMIN_PASSWORD = "inserisci-una-password-di-almeno-12-caratteri"
py -3 server.py
```

Apri `http://127.0.0.1:8000` per il sito e `http://127.0.0.1:8000/admin.html` per l’area gestione. Le credenziali sono configurate con variabili d’ambiente e non sono salvate nei file del sito.

## Prenotazioni e disponibilità

- Le prenotazioni vengono salvate nel database SQLite `data/mare.sqlite3`.
- L’admin può configurare gli orari generali di pranzo e cena, la capienza per ciascun orario e il limite totale per una data.
- Per una singola data può impostare capienze diverse per ogni orario; lasciando il campo vuoto si usa la capienza standard.
- Le prenotazioni includono data, servizio, orario, persone e note, come richiesto. Gli eventuali parametri UTM vengono conservati e mostrati nell’area gestione.
- Le fasce orarie non sono precompilate: vanno inserite dalla gestione quando sono disponibili gli orari ufficiali del Bagno Marè.

## Prima della pubblicazione

Questa è una base funzionante per la revisione locale, non ancora una pubblicazione pronta per Internet. Prima della consegna al cliente vanno aggiunti i dati ufficiali mancanti, verificati orari e contenuti con la scheda informativa, e configurati un hosting con Python, HTTPS e archiviazione persistente del database. Il server incluso è pensato per sviluppo locale; non va esposto direttamente a Internet.

La cartella `data` contiene prenotazioni e va esclusa dal controllo versione e dai backup pubblici. Le credenziali admin vanno impostate nell’ambiente del server e non condivise nel codice.
