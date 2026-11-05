# A Tutto Pelatona Dinguz · Aggiornamento meccaniche

## 5 novembre 2026 — 18 minigiochi

- **Nascondino, Porta Infernale, Castello di Sabbia, Gavettone:** prove a round, decisioni sincronizzate nella stanza, scelta dei bot, rivelazione e uscita dei concorrenti. Isola e porte con interfacce dedicate.
- **Cocco-Bomba:** bomba che passa di persona in persona; a ogni round viene eliminato chi la possiede all'esplosione.
- **Dinguz Dice:** round di reazione sull'emoji, tempi individuali pubblici, eliminazione dell'ultimo/chi sbaglia.
- **Attento al Magma:** round a 21 con dado D10 manuale, eliminazioni e spareggi D5 manuali in parità.
- **Gioco dell'Oca:** 32 caselle e turni reali condivisi; penalità, bonus, pozzo, labirinto, caselle ×2 e rilancio; staffetta fra due coppie per squadra.
- **Lancio dei Dadi:** D12 manuale, quattro tiri di squadra (ripetuti per chi ha pochi compagni) e lanci separati degli NPC visibili.
- **Pesca:** probabilità differenti nelle cinque zone, catture visibili e cronologia.
- **Duelli Fortunati:** HP, turni, avversari selezionabili e blocco del bersaglio consecutivo per squadra quando esistono alternative.
- **Memory e Puzzle:** schemi individuali, cinque minuti per Puzzle, progressi verificabili, record di velocità e punteggi di squadra per classifica individuale.
- **Gara di mangiate:** 3 piatti, fasi rosse penalizzanti, controlli con una piccola cadenza minima e NPC con progressi in tempo reale.
- **Ponte di corda:** barre di precisione progressivamente più strette con zona verde mobile.
- **Corsa a ostacoli:** incremento della difficoltà e ostacoli di tipi diversi, compresi quelli aerei.
- **Raccogli il Cocco:** fisica del cesto con inerzia, difficoltà progressiva, punteggi e bot abili.
- **Sasso Carta Forbice:** torneo di duelli e ruota già introdotti nell'aggiornamento precedente, preservati.
- **Prova libera:** tutti i minigiochi testabili 1 contro 5 bot o 3 team da 4, senza modificare la progressione.

## Collaudi e limiti

Sono stati eseguiti test headless di avvio e completamento delle sfide in entrambe le modalità in Chrome, e controlli sintattici JavaScript. I bot di alcuni giochi di velocità/abilità sono **simulati in base a skill e tempo**, non usano la stessa interfaccia manuale degli umani. La sincronizzazione Firestore con più browser su reti diverse non è stata ancora verificata. Alcuni casi limite (soprattutto 50 giocatori e abbandoni/riconnessioni) richiedono ulteriori test reali.