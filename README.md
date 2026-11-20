# Assistente di Studio per la Dislessia

Un agente AI che aiuta gli studenti di scuola superiore con dislessia a studiare testi lunghi di storia, scienze e materie di indirizzo.

**Autore/Squadra:** Sara Giannattasio, Rosaria Nigro, Desirè Melucci, Lucia Basile- Nevergiveup
**Corso:** Percorso istituti superiori, Biotecnologie e Intelligenza Artificiale (bioERGOtech)

## 1. Il problema

Molti studenti italiani di scuola superiore con dislessia fanno fatica a leggere e capire testi lunghi in materie come storia e scienze. Spesso passano molto tempo a leggere e poi non ricordano i punti principali. Questo rende più difficile studiare per le verifiche e fare i compiti. Le difficoltà di lettura non dipendono dall'intelligenza: per questo un aiuto semplice, sempre disponibile a casa, può togliere fatica e lasciare più tempo per capire la materia.

## 2. La soluzione

L'agente riceve un testo di studio e restituisce sempre la stessa risposta, in quattro parti:

1. **Riassunto:** massimo 5 frasi corte (15 parole ciascuna al massimo).
2. **Parole difficili:** da 5 a 8 parole, con una spiegazione semplice.
3. **Punti importanti:** da 3 a 5 punti elenco da ricordare.
4. **Domande:** 2 domande semplici per controllare di aver capito.

Alla fine l'agente ricorda sempre: "Controlla con il libro o con l'insegnante."

Se lo studente scrive "troppo difficile" o "più corto", l'agente riscrive la risposta.

Il formato è sempre uguale perché per uno studente con dislessia un ordine prevedibile rende la lettura meno faticosa.

Se il testo è troppo corto o non è di studio, l'agente non risponde a caso: chiede un testo migliore. Se il testo non è in italiano, lo traduce e lo dice.

## 3. Come funziona (architettura)

| Componente | Nel mio agente |
|---|---|
| Percezione | Lo studente incolla un testo di storia, scienze dei materiali, gnatologia |
| Pianificazione | L'agente decide se il testo va bene, controlla i limiti di lunghezza, poi segue i 4 passi |
| Uso di strumenti | Un modello linguistico (Claude/ChatGPT), guidato da istruzioni scritte in `prompt.txt` |
| Memoria | Ricorda la conversazione corrente (non salva nulla dopo) |
| Feedback | Lo studente può chiedere "troppo difficile" o "più corto" |

Non c'è codice: l'agente è costruito con istruzioni (prompt) su un modello linguistico. È un prototipo semplice, pensato per mostrare l'idea.

## 4. Come usarlo (setup)

1. Apri una nuova chat con Claude o ChatGPT.
2. Copia tutto il contenuto del file `prompt.txt` e incollalo come primo messaggio.
3. In un nuovo messaggio incolla il testo da studiare (1-2 paragrafi). Non inserire nome, cognome, indirizzo o altre informazioni private.
4. Leggi la risposta. Se serve, scrivi "troppo difficile" o "più corto".

## 5. Test sui casi limite

Ho provato l'agente con input difficili, anche su materie di indirizzo. Qui sotto trovi i risultati.

| # | Input | Risultato atteso | Risultato reale | Stato |
|---|---|---|---|---|
| 1 | Presentazione sui denti (testo incollato) | Riassunto nel formato a 4 parti | Riassunto corretto | superato |
| 2 | Guida sulla classificazione di Kennedy | Riassunto semplice | Riassunto fatto, ma le immagini della guida non vengono lette | parziale |
| 3 | Presentazione del Barocco | Riassunto di massimo 5 frasi | Riassunto troppo lungo | fallito (prima versione del prompt) |

**Modifica fatta dopo i test:** nel `prompt.txt` ho aggiunto il controllo dei limiti prima di rispondere (numero di frasi e di parole). Il test 3 va rifatto con la nuova versione e il risultato aggiornato in questa tabella.

**Problemi che ho notato:**

- I testi specialistici hanno termini tecnici che restano difficili anche spiegati.
- Le presentazioni hanno poco testo e molte immagini: l'agente legge solo il testo e può perdere informazioni.
- Per rispettare i limiti di lunghezza, l'agente lascia fuori dettagli.
- L'agente può sbagliare. Per questo lo studente deve sempre controllare con il libro.

## 6. Limiti e prossimi passi

**Limiti attuali:**

- Non è stato provato con studenti con dislessia. Funziona solo come prototipo.
- Non legge le immagini né i file: solo testo incollato.
- Non è un sostituto dell'insegnante o del libro.
- Le risposte non sono controllate da un esperto.

**Prossimi passi:**

- Provarlo con studenti e insegnanti e raccogliere i loro commenti.
- Usare caratteri e colori pensati per la dislessia.
- Aggiungere la lettura ad alta voce.
- Permettere di caricare foto o PDF delle pagine del libro.

## Demo

Video della dimostrazione: https://drive.google.com/file/d/1eLrM12cj1_yO9EhCzx3AmKiH8NDWURqv/view?usp=sharing

https://drive.google.com/file/d/1wJFHkuAb-K-H-kPnoBb0pRnAKl-wi-uW/view?usp=sharing

## Revisione etica

Vedi il file [`ethics-review.md`](ethics-review.md).
