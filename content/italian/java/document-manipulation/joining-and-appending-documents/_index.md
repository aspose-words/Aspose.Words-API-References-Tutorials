---
title: Unire e aggiungere documenti in Aspose.Words per Java
linktitle: Unire e aggiungere documenti
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Scopri come unire e aggiungere documenti senza sforzo usando Aspose.Words per Java. Mantieni la formattazione, gestisci intestazioni, piè di pagina e altro ancora.
type: docs
weight: 30
url: /it/java/document-manipulation/joining-and-appending-documents/
---

## Introduzione all'unione e all'aggiunta di documenti in Aspose.Words per Java

In questo tutorial, esploreremo come unire e aggiungere documenti utilizzando la libreria Aspose.Words per Java. Imparerai come unire senza problemi più documenti preservandone formattazione e struttura.

## Prerequisiti

Prima di iniziare, assicurati di aver configurato Aspose.Words per Java API nel tuo progetto Java.

## Opzioni di unione dei documenti

### Aggiunta semplice

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Aggiungi con le opzioni del formato di importazione

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### Aggiungi al documento vuoto

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Aggiungi con conversione numero pagina

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // Convertire i campi NUMPAGES
dstDoc.updatePageLayout(); // Aggiorna il layout della pagina per una numerazione corretta
```

## Gestione di diverse impostazioni di pagina

Quando si allegano documenti con diverse impostazioni di pagina:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// Assicurarsi che le impostazioni di configurazione della pagina corrispondano al documento di destinazione
```

## Unire documenti con stili diversi

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## Comportamento di stile intelligente

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## Inserimento di documenti con DocumentBuilder

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Mantenere la numerazione delle fonti

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Gestione delle caselle di testo

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Gestione di intestazioni e piè di pagina

### Collegamento di intestazioni e piè di pagina

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Scollegamento di intestazioni e piè di pagina

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Conclusione

Aspose.Words per Java fornisce strumenti flessibili e potenti per unire e aggiungere documenti, sia che tu debba mantenere la formattazione, gestire diverse impostazioni di pagina o gestire intestazioni e piè di pagina. Sperimenta queste tecniche per soddisfare le tue specifiche esigenze di elaborazione dei documenti.

## Domande frequenti

### Come posso unire senza problemi documenti con stili diversi?

 Per unire documenti con stili diversi, utilizzare`ImportFormatMode.USE_DESTINATION_STYLES` durante l'aggiunta.

### Posso mantenere la numerazione delle pagine quando allego documenti?

 Sì, puoi preservare la numerazione delle pagine utilizzando`convertNumPageFieldsToPageRef` metodo e aggiornamento del layout della pagina.

### Che cosa si intende per comportamento intelligente?

 Smart Style Behavior aiuta a mantenere stili coerenti quando si aggiungono documenti. Usalo con`ImportFormatOptions` per ottenere risultati migliori.

### Come posso gestire le caselle di testo quando allego documenti?

Impostato`importFormatOptions.setIgnoreTextBoxes(false)` per includere caselle di testo durante l'aggiunta.

### Cosa succede se voglio collegare/scollegare intestazioni e piè di pagina tra documenti?

 È possibile collegare intestazioni e piè di pagina con`linkToPrevious(true)` o scollegarli con`linkToPrevious(false)` secondo necessità.