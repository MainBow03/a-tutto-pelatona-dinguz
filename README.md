# 🏝️ A Tutto Pelatona Dinguz

Gioco browser **reale e interattivo**, realizzato in HTML/CSS/JavaScript senza build, destinato a **GitHub Pages**. È una **nuova implementazione** basata sulle specifiche e sugli screenshot, non una patch del progetto Emergent originale: il codice originale non era in allegato.

## Avvio immediato

Apri `index.html` o, preferibilmente, avvia un server locale e visita il sito:

```bash
python -m http.server 8080
# apri http://localhost:8080
```

Se Firebase non è configurato o non risponde, si avvia in **modalità demo locale**: puoi creare una stanza, riempirla di NPC e giocare con tutte le fasi. La demo è archiviata nel `localStorage` del browser; non sincronizza dispositivi diversi.

## Pubblicare su GitHub Pages

1. I file del gioco sono già presenti nella radice di questa repository.
2. Repository → **Settings** → **Pages** → Build and deployment → **Deploy from a branch**, branch `main` e cartella `/ (root)`.
3. Apri il link Pages. Se Firebase è configurato puoi creare stanza e comunicare il suo codice agli amici.

## Abilitare il multiplayer Firestore

Il file `game.js` contiene la configurazione del progetto Firebase ricevuta nelle specifiche (`mario-party-style-game`). Verifica che il progetto sia ancora quello corretto. In Firebase Console:

1. Authentication → Sign-in method → **Anonymous** → Enable.
2. Firestore Database → crea il database se non esiste.
3. Firestore Database → Rules → sostituisci con il contenuto di **`firestore.rules`** e pubblica.
4. L’app usa la raccolta `dinguz_rooms/{CODICE}`. Tutti gli utenti devono essere autenticati anonimamente: se non è possibile la connessione, comparirà la modalità demo locale.

**Sicurezza:** le regole sono pensate per una versione tra amici e consentono ai membri della stanza di modificare lo stato del gioco. Non sono antifrode: contro giocatori ostili sono necessari un backend autorevole (Cloud Functions / server) e controlli di validità delle mosse. I dialoghi sono *privati nell’interfaccia*, ma sono salvati nel documento condiviso e **non sono criptati o segreti per gli altri membri con accesso tecnico al documento**. Per vera privacy spostali in documenti privati con regole per utente.

## Cosa include questa versione

- 98 personaggi con i link immagine forniti nel testo, comprese **Candace, Vanessa, Perry e Ferb** e le loro **11 skin**.
- Home, statistiche locali, valuta, mini shop, sblocco casuale da **120 monete**, vittoria da **400 monete**, skin e inventario.
- Lobby online tramite codice o elenco, scelta personaggio senza duplicati, riempimento con NPC, da 8 a 50 partecipanti e da 2 a 6 squadre.
- Distribuzione prima dei **giocatori umani su team distinti**, poi riempimento equilibrato con NPC (es. 4 umani / 3 team → 2,1,1).
- Fasi sincronizzate: team → sociale → sfida → risultato → votazione → cerimonia → nuova puntata; merge e finale a prove.
- Quattro dialoghi: chiacchiera, battuta, strategia, punzecchia, con più testi, relazioni, pettegolezzi NPC e vincolo di **uno o due dialoghi per episodio con NPC differenti**.
- 18 minigiochi a **rotazione senza ripetizioni prima del completamento del mazzo**. Alcuni sono implementazioni leggere delle regole originali, e non ancora giochi competitivi multi-round completi.
- Mini giochi particolarmente interattivi: cesto con inerzia per i cocchi, pesca con cattura visibile, memory 32 carte, puzzle in tre stage (5 minuti), Dinguz Dice con tempi visibili, corsa con salti e ostacoli, gara di mangiate, duelli sequenziali con registro, dado manuale e tiebreaker, gavettone a quattro zone, nascondino con luoghi occupati.
- Votazioni segrete, bot che votano secondo relazioni, idoli, falò con rivelazione progressiva, spareggio manuale con dado D5, comeback e classifica finale, classifica dei cuori e dei voti.
- Salvataggio locale di shop e statistiche; Firestore per lo stato condiviso della stanza; tentativo di passaggio host dopo **45 secondi** d’inattività.

## Limiti importanti

Questa è una prima versione **giocabile da espandere**: non è la replica completa del codice Emergent visto negli screenshot. I minigiochi Porta Infernale, Nascondino, Cocco-Bomba, Sasso-Carta-Forbice, Gioco dell'Oca e Gavettone funzionano al momento con un turno o un punteggio semplificato, non con tutti i round e le regole dettagliate del progetto di origine. La selezione delle skin include le 11 immagini nuove ma non l'intero catalogo di skin storiche descritto nel testo. Il salvataggio di progressione è locale al browser, non a un account Firebase personale. I PNG esterni possono essere bloccati da Pinterest in certi browser. Al momento non è inclusa una protezione lato server contro cheating, né un sistema di disconnessione/riconnessione completamente testato in produzione.

**Verifica prima di una partita multiplayer seria:** prova due finestre anonime o due dispositivi con Firebase attivo, controlla la sincronizzazione delle stanze e i permessi di Firestore. Per usare/modificare direttamente il progetto originale, serve il suo sorgente.