# Revisione etica

Progetto: Assistente di Studio per la Dislessia

L'agente è pensato per studenti di scuola superiore, quindi per ragazzi in gran parte minorenni. Per questo ho guardato con attenzione quattro aspetti.

## 1\. Privacy

**Rischio:** lo studente potrebbe incollare nel testo dati personali (nome, scuola, compiti con il proprio nome) o testi di altri.

**Cosa faccio:**

* L'agente non chiede dati personali e non salva niente tra una chat e l'altra.
* Nelle istruzioni d'uso scrivo: "Non incollare nome, cognome, indirizzo o altre informazioni private".
* Il prototipo funziona su una piattaforma esterna (Claude): i testi vengono inviati a un servizio online. Gli studenti minorenni dovrebbero usarlo con il permesso di un genitore o di un insegnante, secondo le regole della piattaforma.

**Cosa resta aperto:** non ho controllato in dettaglio come la piattaforma tratta i dati. Prima di un uso in classe va verificato.

## 2\. Pregiudizi (bias)

**Rischio:** il modello può semplificare un testo togliendo punti di vista o dettagli, soprattutto in storia, dove contano le prospettive. Può anche funzionare meglio con alcuni argomenti o in alcune lingue.

**Cosa faccio:**

* Nelle regole c'è: "Non inventare informazioni che non sono nel testo".
* L'agente riassume solo il testo dato, non aggiunge opinioni.

**Cosa resta aperto:** il riassunto è sempre una scelta di cosa tenere e cosa togliere. L'agente può togliere informazioni importanti senza dirlo.

## 3\. Trasparenza

**Rischio:** lo studente potrebbe pensare che l'agente sia sempre corretto o che sia una persona.

**Cosa faccio:**

* Nelle istruzioni l'agente ricorda alla fine: "Controlla con il libro o con l'insegnante".
* Se il testo è in inglese, l'agente dice che l'ha tradotto.
* Nel README scrivo i limiti e i test falliti.

**Cosa resta aperto:** il messaggio di controllo può essere ignorato. Lo studente deve capire che è uno strumento di aiuto, non una fonte.

## 4\. Responsabilità

**Rischio:** se l'agente sbaglia un riassunto e lo studente prende un voto basso, chi è responsabile?

**Cosa faccio:**

* L'agente è solo un aiuto per studiare, non un sostituto del libro e dell'insegnante.
* Documento gli errori trovati nei test.

**Chi risponde:** io sono responsabile del progetto. Non posso promettere che le risposte siano sempre giuste. Un uso reale con studenti dovrebbe avere la supervisione di insegnanti e, per la dislessia, di specialisti.

## Conclusione

Il progetto può aiutare ma non è privo di rischi. Le due cose più importanti: **non incollare dati personali** e **controllare sempre con il libro**. Prima di un uso reale servono prove con studenti, insegnanti ed esperti di dislessia.

