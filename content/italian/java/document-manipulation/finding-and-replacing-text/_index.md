---
title: Trovare e sostituire il testo in Aspose.Words per Java
linktitle: Trovare e sostituire il testo
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Scopri come trovare e sostituire il testo nei documenti di Word con Aspose.Words per Java. Guida passo passo con esempi di codice. Migliora le tue capacità di manipolazione dei documenti Java.
type: docs
weight: 15
url: /it/java/document-manipulation/finding-and-replacing-text/
---

## Introduzione alla ricerca e alla sostituzione del testo in Aspose.Words per Java

Aspose.Words per Java è una potente API Java che ti consente di lavorare con documenti Word a livello di codice. Uno dei compiti più comuni quando si ha a che fare con documenti Word è trovare e sostituire il testo. Se hai bisogno di aggiornare i segnaposto nei modelli o eseguire manipolazioni di testo più complesse, Aspose.Words per Java può aiutarti a raggiungere i tuoi obiettivi in modo efficiente.

## Prerequisiti

Prima di approfondire i dettagli sulla ricerca e la sostituzione del testo, assicurati di disporre dei seguenti prerequisiti:

- Ambiente di sviluppo Java
- Aspose.Words per la libreria Java
- Un documento Word di esempio con cui lavorare

 È possibile scaricare la libreria Aspose.Words per Java da[Qui](https://releases.aspose.com/words/java/).

## Trovare e sostituire testo semplice

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Creare un DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Trova e sostituisci il testo
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Salva il documento modificato
doc.save("modified-document.docx");
```

 In questo esempio, carichiamo un documento Word, creiamo un file`DocumentBuilder` e utilizzare il file`replace` metodo per trovare e sostituire il "vecchio testo" con il "nuovo testo" all'interno del documento.

## Utilizzo delle espressioni regolari

Le espressioni regolari forniscono potenti funzionalità di corrispondenza dei modelli per la ricerca e la sostituzione del testo. Aspose.Words per Java supporta le espressioni regolari per operazioni di ricerca e sostituzione più avanzate.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Creare un DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);

// Utilizza le espressioni regolari per trovare e sostituire il testo
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

// Salva il documento modificato
doc.save("modified-document.docx");
```

In questo esempio utilizziamo un modello di espressione regolare per trovare e sostituire il testo all'interno del documento.

## Ignorare il testo all'interno dei campi

È possibile configurare Aspose.Words per ignorare il testo all'interno dei campi durante l'esecuzione di operazioni di ricerca e sostituzione.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza FindReplaceOptions e imposta IgnoreFields su true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

// Utilizza le opzioni quando sostituisci il testo
doc.getRange().replace("text-to-replace", "new-text", options);

// Salva il documento modificato
doc.save("modified-document.docx");
```

Ciò è utile quando si desidera escludere la sostituzione del testo all'interno dei campi, ad esempio i campi di unione.

## Ignorare il testo all'interno di Elimina revisioni

È possibile configurare Aspose.Words per ignorare il testo all'interno delle revisioni di eliminazione durante le operazioni di ricerca e sostituzione.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza FindReplaceOptions e imposta IgnoreDeleted su true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

// Utilizza le opzioni quando sostituisci il testo
doc.getRange().replace("text-to-replace", "new-text", options);

// Salva il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di escludere dalla sostituzione il testo contrassegnato per l'eliminazione nelle modifiche rilevate.

## Ignorare il testo all'interno delle revisioni di inserimento

È possibile configurare Aspose.Words per ignorare il testo all'interno delle revisioni di inserimento durante le operazioni di ricerca e sostituzione.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza FindReplaceOptions e imposta IgnoreInserted su true
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

// Utilizza le opzioni quando sostituisci il testo
doc.getRange().replace("text-to-replace", "new-text", options);

// Salva il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di escludere dalla sostituzione il testo contrassegnato come inserito nelle modifiche rilevate.

## Sostituzione del testo con HTML

È possibile utilizzare Aspose.Words per Java per sostituire il testo con contenuto HTML.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza FindReplaceOptions con un callback di sostituzione personalizzato
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

// Utilizza le opzioni quando sostituisci il testo
doc.getRange().replace("text-to-replace", "new-html-content", options);

// Salva il documento modificato
doc.save("modified-document.docx");
```

 In questo esempio utilizziamo un custom`ReplaceWithHtmlEvaluator` per sostituire il testo con contenuto HTML.

## Sostituzione del testo nelle intestazioni e nei piè di pagina

Puoi trovare e sostituire il testo nelle intestazioni e nei piè di pagina del tuo documento Word.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Ottieni la raccolta di intestazioni e piè di pagina
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

// Scegli il tipo di intestazione o piè di pagina in cui desideri sostituire il testo (ad esempio HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// Crea un'istanza FindReplaceOptions e applicala all'intervallo del piè di pagina
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

// Salva il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di eseguire sostituzioni di testo specificatamente nelle intestazioni e nei piè di pagina.

## Visualizzazione delle modifiche per gli ordini di intestazione e piè di pagina

Puoi utilizzare Aspose.Words per mostrare le modifiche agli ordini di intestazione e piè di pagina nel tuo documento.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Ottieni la prima sezione
Section firstPageSection = doc.getFirstSection();

// Crea un'istanza FindReplaceOptions e applicala all'intervallo del documento
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//Sostituisci il testo che influisce sugli ordini di intestazione e piè di pagina
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

// Salva il documento modificato
doc.save("modified-document.docx");
```

Ciò ti consente di visualizzare le modifiche relative agli ordini di intestazione e piè di pagina nel tuo documento.

## Sostituzione del testo con campi

È possibile sostituire il testo con campi utilizzando Aspose.Words per Java.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza FindReplaceOptions e imposta un callback di sostituzione personalizzato per i campi
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

// Utilizza le opzioni quando sostituisci il testo
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

// Salva il documento modificato
doc.save("modified-document.docx");
```

 In questo esempio, sostituiamo il testo con campi e specifichiamo il tipo di campo (ad esempio,`FieldType.FIELD_MERGE_FIELD`).

## Sostituzione con un valutatore

È possibile utilizzare un valutatore personalizzato per determinare dinamicamente il testo sostitutivo.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza FindReplaceOptions e imposta un callback di sostituzione personalizzato
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

// Utilizza le opzioni quando sostituisci il testo
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

// Salva il documento modificato
doc.save("modified-document.docx");
```

In questo esempio, utilizziamo un valutatore personalizzato (`MyReplaceEvaluator`) per sostituire il testo.

## Sostituzione con Regex

Aspose.Words per Java ti consente di sostituire il testo utilizzando espressioni regolari.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Utilizza le espressioni regolari per trovare e sostituire il testo
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

// Salva il documento modificato
doc.save("modified-document.docx");
```

In questo esempio utilizziamo un modello di espressione regolare per trovare e sostituire il testo all'interno del documento.

## Riconoscimento e sostituzioni all'interno dei modelli di sostituzione

È possibile riconoscere e apportare sostituzioni all'interno di modelli di sostituzione utilizzando Aspose.Words per Java.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

//Crea un'istanza FindReplaceOptions con UseSubstitutions impostato su true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

// Utilizza le opzioni quando sostituisci il testo con un motivo
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

// Salva il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di eseguire sostituzioni all'interno dei modelli di sostituzione per sostituzioni più avanzate.

## Sostituzione con una stringa

Puoi sostituire il testo con una semplice stringa usando Aspose.Words per Java.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Sostituisci il testo con una stringa
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

// Salva il documento modificato
doc.save("modified-document.docx");
```

In questo esempio, sostituiamo "text-to-replace" con "new-string" all'interno del documento.

## Utilizzo dell'ordine legacy

È possibile utilizzare l'ordine precedente quando si eseguono operazioni di ricerca e sostituzione.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Crea un'istanza FindReplaceOptions e imposta UseLegacyOrder su true
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

// Utilizza le opzioni quando sostituisci il testo
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

// Salva il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di utilizzare l'ordine legacy per le operazioni di ricerca e sostituzione.

## Sostituzione del testo in una tabella

Puoi trovare e sostituire il testo all'interno delle tabelle del tuo documento Word.

```java
// Caricare il documento
Document doc = new Document("your-document.docx");

// Ottieni una tabella specifica (ad esempio, la prima tabella)
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

// Utilizzare FindReplaceOptions per sostituire il testo nella tabella
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

// Salva il documento modificato
doc.save("modified-document.docx");
```

Ciò consente di eseguire sostituzioni di testo specificatamente all'interno delle tabelle.

## Conclusione

Aspose.Words per Java fornisce funzionalità complete per trovare e sostituire testo all'interno di documenti Word. Sia che tu abbia bisogno di eseguire semplici sostituzioni di testo o operazioni più avanzate utilizzando espressioni regolari, manipolazioni di campi o analizzatori personalizzati, Aspose.Words per Java ti copre. Assicurati di esplorare l'ampia documentazione e gli esempi forniti da Aspose per sfruttare tutto il potenziale di questa potente libreria Java.

## Domande frequenti

### Come posso scaricare Aspose.Words per Java?

 È possibile scaricare Aspose.Words per Java dal sito Web visitando[questo collegamento](https://releases.aspose.com/words/java/).

### Posso utilizzare le espressioni regolari per la sostituzione del testo?

Sì, puoi utilizzare le espressioni regolari per la sostituzione del testo in Aspose.Words per Java. Ciò consente di eseguire operazioni di ricerca e sostituzione più avanzate e flessibili.

### Come posso ignorare il testo all'interno dei campi durante la sostituzione?

 Per ignorare il testo all'interno dei campi durante la sostituzione, è possibile impostare il file`IgnoreFields` proprietà del`FindReplaceOptions` A`true`Ciò garantisce che il testo all'interno dei campi, ad esempio i campi di unione, sia escluso dalla sostituzione.

### Posso sostituire il testo all'interno di intestazioni e piè di pagina?

 Sì, puoi sostituire il testo all'interno delle intestazioni e dei piè di pagina del tuo documento Word. Basta accedere all'intestazione o al piè di pagina appropriati e utilizzare il file`replace` metodo con quello desiderato`FindReplaceOptions`.

### A cosa serve l'opzione UseLegacyOrder?

 IL`UseLegacyOrder` opzione dentro`FindReplaceOptions` consente di utilizzare l'ordine precedente durante l'esecuzione di operazioni di ricerca e sostituzione. Ciò può essere utile in alcuni scenari in cui si desidera il comportamento dell'ordine legacy.