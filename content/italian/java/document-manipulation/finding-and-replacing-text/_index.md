---
title: Trovare e sostituire il testo in Aspose.Words per Java
linktitle: Trovare e sostituire il testo
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Scopri come trovare e sostituire testo nei documenti Word con Aspose.Words per Java. Guida passo passo con esempi di codice. Migliora le tue capacità di manipolazione dei documenti Java.
type: docs
weight: 15
url: /it/java/document-manipulation/finding-and-replacing-text/
---

## Introduzione alla ricerca e sostituzione del testo in Aspose.Words per Java

Aspose.Words per Java è una potente API Java che consente di lavorare con documenti Word a livello di programmazione. Una delle attività comuni quando si ha a che fare con documenti Word è trovare e sostituire testo. Sia che si debbano aggiornare segnaposto nei modelli o eseguire manipolazioni di testo più complesse, Aspose.Words per Java può aiutare a raggiungere i propri obiettivi in modo efficiente.

## Prerequisiti

Prima di addentrarci nei dettagli della ricerca e sostituzione del testo, assicurati di avere soddisfatto i seguenti prerequisiti:

- Ambiente di sviluppo Java
- Libreria Aspose.Words per Java
- Un esempio di documento Word con cui lavorare

 Puoi scaricare la libreria Aspose.Words per Java da[Qui](https://releases.aspose.com/words/java/).

## Trovare e sostituire testo semplice

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Crea un DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Trova e sostituisci testo
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Salvare il documento modificato
doc.save("modified-document.docx");
```

 In questo esempio, carichiamo un documento Word, creiamo un`DocumentBuilder` , e utilizzare il`replace` Metodo per trovare e sostituire "vecchio-testo" con "nuovo-testo" all'interno del documento.

## Utilizzo delle espressioni regolari

Le espressioni regolari forniscono potenti capacità di pattern matching per la ricerca e la sostituzione di testo. Aspose.Words per Java supporta espressioni regolari per operazioni di ricerca e sostituzione più avanzate.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Crea un DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Utilizzare espressioni regolari per trovare e sostituire il testo
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Salvare il documento modificato
doc.save("modified-document.docx");
```

In questo esempio utilizziamo un modello di espressione regolare per trovare e sostituire il testo all'interno del documento.

## Ignorare il testo all'interno dei campi

È possibile configurare Aspose.Words in modo che ignori il testo all'interno dei campi quando si eseguono operazioni di ricerca e sostituzione.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza di FindReplaceOptions e imposta IgnoreFields su true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Utilizzare le opzioni quando si sostituisce il testo
doc.getRange().replace("text-to-replace", "new-text", options);

// Salvare il documento modificato
doc.save("modified-document.docx");
```

Questa opzione è utile quando si desidera escludere la sostituzione del testo all'interno dei campi, ad esempio nei campi di unione.

## Ignorare il testo all'interno delle revisioni di eliminazione

È possibile configurare Aspose.Words in modo che ignori il testo all'interno delle revisioni di eliminazione durante le operazioni di ricerca e sostituzione.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza di FindReplaceOptions e imposta IgnoreDeleted su true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Utilizzare le opzioni quando si sostituisce il testo
doc.getRange().replace("text-to-replace", "new-text", options);

// Salvare il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di escludere la sostituzione del testo contrassegnato per l'eliminazione nelle revisioni tracciate.

## Ignorare il testo all'interno delle revisioni di inserimento

È possibile configurare Aspose.Words in modo che ignori il testo all'interno delle revisioni di inserimento durante le operazioni di ricerca e sostituzione.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza di FindReplaceOptions e imposta IgnoreInserted su true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Utilizzare le opzioni quando si sostituisce il testo
doc.getRange().replace("text-to-replace", "new-text", options);

// Salvare il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di escludere dalla sostituzione il testo contrassegnato come inserito nelle revisioni tracciate.

## Sostituzione del testo con HTML

È possibile utilizzare Aspose.Words per Java per sostituire il testo con contenuto HTML.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza di FindReplaceOptions con un callback di sostituzione personalizzato
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Utilizzare le opzioni quando si sostituisce il testo
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Salvare il documento modificato
doc.save("modified-document.docx");
```

 In questo esempio, utilizziamo un personalizzato`ReplaceWithHtmlEvaluator` per sostituire il testo con contenuto HTML.

## Sostituzione del testo nelle intestazioni e nei piè di pagina

È possibile trovare e sostituire il testo nelle intestazioni e nei piè di pagina del documento Word.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Ottieni la raccolta di intestazioni e piè di pagina
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// Seleziona il tipo di intestazione o piè di pagina in cui vuoi sostituire il testo (ad esempio, HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// Crea un'istanza di FindReplaceOptions e applicala all'intervallo del piè di pagina
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// Salvare il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di effettuare sostituzioni di testo specifiche nelle intestazioni e nei piè di pagina.

## Visualizzazione delle modifiche per gli ordini di intestazione e piè di pagina

Puoi utilizzare Aspose.Words per mostrare le modifiche apportate all'ordine delle intestazioni e dei piè di pagina nel tuo documento.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Ottieni la prima sezione
Section firstPageSection = doc.getFirstSection();

//Crea un'istanza di FindReplaceOptions e applicala all'intervallo del documento
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

// Sostituisci il testo che influisce sugli ordini di intestazione e piè di pagina
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Salvare il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di visualizzare le modifiche relative all'ordine delle intestazioni e dei piè di pagina nel documento.

## Sostituzione del testo con i campi

È possibile sostituire il testo con i campi utilizzando Aspose.Words per Java.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza di FindReplaceOptions e imposta un callback di sostituzione personalizzato per i campi
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Utilizzare le opzioni quando si sostituisce il testo
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Salvare il documento modificato
doc.save("modified-document.docx");
```

 In questo esempio, sostituiamo il testo con i campi e specifichiamo il tipo di campo (ad esempio,`FieldType.FIELD_MERGE_FIELD`).

## Sostituzione con un valutatore

È possibile utilizzare un valutatore personalizzato per determinare dinamicamente il testo sostitutivo.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza di FindReplaceOptions e imposta un callback di sostituzione personalizzato
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Utilizzare le opzioni quando si sostituisce il testo
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Salvare il documento modificato
doc.save("modified-document.docx");
```

In questo esempio, utilizziamo un valutatore personalizzato (`MyReplaceEvaluator`) per sostituire il testo.

## Sostituzione con Regex

Aspose.Words per Java consente di sostituire il testo utilizzando espressioni regolari.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Utilizzare espressioni regolari per trovare e sostituire il testo
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// Salvare il documento modificato
doc.save("modified-document.docx");
```

In questo esempio utilizziamo un modello di espressione regolare per trovare e sostituire il testo all'interno del documento.

## Riconoscimento e sostituzioni all'interno dei modelli di sostituzione

È possibile riconoscere ed effettuare sostituzioni all'interno di modelli di sostituzione utilizzando Aspose.Words per Java.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza di FindReplaceOptions con UseSubstitutions impostato su true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Utilizzare le opzioni quando si sostituisce il testo con un modello
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Salvare il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di effettuare sostituzioni all'interno dei modelli di sostituzione per sostituzioni più avanzate.

## Sostituzione con una stringa

È possibile sostituire il testo con una semplice stringa utilizzando Aspose.Words per Java.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Sostituisci il testo con una stringa
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Salvare il documento modificato
doc.save("modified-document.docx");
```

In questo esempio, sostituiamo "text-to-replace" con "new-string" all'interno del documento.

## Utilizzo dell'ordine legacy

È possibile utilizzare l'ordine legacy quando si eseguono operazioni di ricerca e sostituzione.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza di FindReplaceOptions e imposta UseLegacyOrder su true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Utilizzare le opzioni quando si sostituisce il testo
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Salvare il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di utilizzare l'ordine legacy per le operazioni di ricerca e sostituzione.

## Sostituzione del testo in una tabella

È possibile trovare e sostituire il testo all'interno delle tabelle nel documento Word.

```java
// Carica il documento
Document doc = new Document("your-document.docx");

// Ottieni una tabella specifica (ad esempio, la prima tabella)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

//Utilizzare FindReplaceOptions per sostituire il testo nella tabella
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Salvare il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di eseguire sostituzioni di testo specifiche all'interno delle tabelle.

## Conclusione

Aspose.Words per Java offre funzionalità complete per trovare e sostituire testo nei documenti Word. Che tu debba eseguire semplici sostituzioni di testo o operazioni più avanzate utilizzando espressioni regolari, manipolazioni di campo o valutatori personalizzati, Aspose.Words per Java ha ciò che fa per te. Assicurati di esplorare la documentazione completa e gli esempi forniti da Aspose per sfruttare appieno il potenziale di questa potente libreria Java.

## Domande frequenti

### Come posso scaricare Aspose.Words per Java?

 È possibile scaricare Aspose.Words per Java dal sito Web visitando[questo collegamento](https://releases.aspose.com/words/java/).

### Posso usare espressioni regolari per sostituire il testo?

Sì, puoi usare espressioni regolari per la sostituzione del testo in Aspose.Words per Java. Ciò ti consente di eseguire operazioni di ricerca e sostituzione più avanzate e flessibili.

### Come posso ignorare il testo all'interno dei campi durante la sostituzione?

Per ignorare il testo all'interno dei campi durante la sostituzione, è possibile impostare`IgnoreFields` proprietà del`FindReplaceOptions` A`true`Ciò garantisce che il testo all'interno dei campi, come i campi di unione, venga escluso dalla sostituzione.

### Posso sostituire il testo nelle intestazioni e nei piè di pagina?

 Sì, puoi sostituire il testo all'interno delle intestazioni e dei piè di pagina del tuo documento Word. Accedi semplicemente all'intestazione o al piè di pagina appropriati e usa il`replace` metodo con il desiderato`FindReplaceOptions`.

### A cosa serve l'opzione UseLegacyOrder?

 IL`UseLegacyOrder` opzione in`FindReplaceOptions` consente di usare l'ordine legacy quando si eseguono operazioni di ricerca e sostituzione. Ciò può essere utile in determinati scenari in cui è desiderato il comportamento dell'ordine legacy.