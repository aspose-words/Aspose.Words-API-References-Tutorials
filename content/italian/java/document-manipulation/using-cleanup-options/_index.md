---
title: Utilizzo delle opzioni di pulizia in Aspose.Words per Java
linktitle: Utilizzo delle opzioni di pulizia
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Migliora la chiarezza del documento con Aspose.Words per le opzioni di pulizia Java. Scopri come rimuovere paragrafi vuoti, aree inutilizzate e altro ancora.
type: docs
weight: 10
url: /it/java/document-manipulation/using-cleanup-options/
---

## Introduzione all'utilizzo delle opzioni di pulizia in Aspose.Words per Java

In questo tutorial esploreremo come utilizzare le opzioni di pulizia in Aspose.Words per Java per manipolare e ripulire i documenti durante il processo di stampa unione. Le opzioni di pulizia ti consentono di controllare vari aspetti della pulizia del documento, come la rimozione di paragrafi vuoti, aree inutilizzate e altro.

## Prerequisiti

 Prima di iniziare, assicurati di avere la libreria Aspose.Words per Java integrata nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/words/java/).

## Passaggio 1: rimozione dei paragrafi vuoti

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserisci campi di unione
FieldMergeField mergeFieldOption1 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_1");
mergeFieldOption1.setFieldName("Option_1");
builder.write(" ? ");
FieldMergeField mergeFieldOption2 = (FieldMergeField) builder.insertField("MERGEFIELD", "Option_2");
mergeFieldOption2.setFieldName("Option_2");

// Imposta le opzioni di pulizia
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS);

// Abilita i paragrafi di pulizia con segni di punteggiatura
doc.getMailMerge().setCleanupParagraphsWithPunctuationMarks(true);

// Esegui la stampa unione
doc.getMailMerge().execute(new String[] { "Option_1", "Option_2" }, new Object[] { null, null });

// Salva il documento
doc.save("WorkingWithCleanupOptions.CleanupParagraphsWithPunctuationMarks.docx");
```

In questo esempio creiamo un nuovo documento, inseriamo campi di unione e impostiamo le opzioni di pulizia per rimuovere i paragrafi vuoti. Inoltre, consentiamo la rimozione dei paragrafi con segni di punteggiatura. Dopo aver eseguito la stampa unione, il documento viene salvato con applicata la pulizia specificata.

## Passaggio 2: rimozione delle regioni non unite

```java
Document doc = new Document("Your Directory Path" + "Mail merge destination - Northwind suppliers.docx");
DataSet data = new DataSet();

// Imposta le opzioni di pulizia per rimuovere le regioni inutilizzate
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS);

// Esegui la stampa unione con le regioni
doc.getMailMerge().executeWithRegions(data);

// Salva il documento
doc.save("WorkingWithCleanupOptions.RemoveUnmergedRegions.docx");
```

In questo esempio, apriamo un documento esistente con aree di unione, impostiamo le opzioni di pulizia per rimuovere le aree inutilizzate, quindi eseguiamo la stampa unione con dati vuoti. Questo processo rimuove automaticamente le regioni inutilizzate dal documento.

## Passaggio 3: rimozione dei campi vuoti

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Imposta le opzioni di pulizia per rimuovere i campi vuoti
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_FIELDS);

// Esegui la stampa unione
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Salva il documento
doc.save("WorkingWithCleanupOptions.RemoveEmptyFields.docx");
```

In questo esempio, apriamo un documento con campi unione, impostiamo le opzioni di pulizia per rimuovere i campi vuoti ed eseguiamo la stampa unione con i dati. Dopo l'unione, tutti i campi vuoti verranno rimossi dal documento.

## Passaggio 4: rimozione dei campi inutilizzati

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Imposta le opzioni di pulizia per rimuovere i campi inutilizzati
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS);

// Esegui la stampa unione
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Salva il documento
doc.save("WorkingWithCleanupOptions.RemoveUnusedFields.docx");
```

In questo esempio, apriamo un documento con campi unione, impostiamo le opzioni di pulizia per rimuovere i campi inutilizzati ed eseguiamo la stampa unione con i dati. Dopo l'unione, tutti i campi inutilizzati verranno rimossi dal documento.

## Passaggio 5: rimozione dei campi contenenti

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Imposta le opzioni di pulizia per rimuovere i campi contenenti
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS);

// Esegui la stampa unione
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Salva il documento
doc.save("WorkingWithCleanupOptions.RemoveContainingFields.docx");
```

In questo esempio, apriamo un documento con campi di unione, impostiamo le opzioni di pulizia per rimuovere i campi che lo contengono ed eseguiamo la stampa unione con i dati. Dopo l'unione, i campi stessi verranno rimossi dal documento.

## Passaggio 6: rimozione delle righe vuote della tabella

```java
Document doc = new Document("Your Directory Path" + "Table with fields.docx");

// Imposta le opzioni di pulizia per rimuovere le righe vuote della tabella
doc.getMailMerge().setCleanupOptions(MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS);

// Esegui la stampa unione
doc.getMailMerge().execute(new String[] { "FullName", "Company", "Address", "Address2", "City" },
    new Object[] { "James Bond", "MI5 Headquarters", "Milbank", "", "London" });

// Salva il documento
doc.save("WorkingWithCleanupOptions.RemoveEmptyTableRows.docx");
```

In questo esempio, apriamo un documento con una tabella e uniamo i campi, impostiamo le opzioni di pulizia per rimuovere le righe vuote della tabella ed eseguiamo la stampa unione con i dati. Dopo l'unione, tutte le righe vuote della tabella verranno rimosse dal documento.

## Conclusione

In questo tutorial hai imparato come utilizzare le opzioni di pulizia in Aspose.Words per Java per manipolare e pulire i documenti durante il processo di stampa unione. Queste opzioni forniscono un controllo capillare sulla pulizia dei documenti, consentendoti di creare facilmente documenti raffinati e personalizzati.

## Domande frequenti

### Quali sono le opzioni di pulizia in Aspose.Words per Java?

Le opzioni di pulizia in Aspose.Words per Java sono impostazioni che consentono di controllare vari aspetti della pulizia dei documenti durante il processo di stampa unione. Ti consentono di rimuovere elementi non necessari come paragrafi vuoti, aree inutilizzate e altro, assicurando che il tuo documento finale sia ben strutturato e rifinito.

### Come posso rimuovere i paragrafi vuoti dal mio documento?

 Per rimuovere i paragrafi vuoti dal tuo documento utilizzando Aspose.Words per Java, puoi impostare il file`MailMergeCleanupOptions.REMOVE_EMPTY_PARAGRAPHS` opzione su true. Ciò eliminerà automaticamente i paragrafi privi di contenuto, risultando in un documento più pulito.

###  Qual è lo scopo del`REMOVE_UNUSED_REGIONS` cleanup option?

 IL`MailMergeCleanupOptions.REMOVE_UNUSED_REGIONS` L'opzione viene utilizzata per rimuovere le regioni in un documento che non hanno dati corrispondenti durante il processo di stampa unione. Aiuta a mantenere il documento in ordine eliminando i segnaposto inutilizzati.

### Posso rimuovere righe di tabella vuote da un documento utilizzando Aspose.Words per Java?

 Sì, puoi rimuovere le righe vuote della tabella da un documento impostando il file`MailMergeCleanupOptions.REMOVE_EMPTY_TABLE_ROWS`opzione di pulizia su true. Ciò eliminerà automaticamente tutte le righe della tabella che non contengono dati, garantendo una tabella ben strutturata nel documento.

###  Cosa succede quando imposto il file`REMOVE_CONTAINING_FIELDS` option?

 Impostazione del`MailMergeCleanupOptions.REMOVE_CONTAINING_FIELDS` L'opzione rimuoverà l'intero campo di unione, compreso il paragrafo che lo contiene, dal documento durante il processo di stampa unione. Ciò è utile quando desideri eliminare i campi unione e il testo associato.

### Come posso rimuovere i campi di unione inutilizzati dal mio documento?

 Per rimuovere i campi di unione inutilizzati da un documento, è possibile impostare il file`MailMergeCleanupOptions.REMOVE_UNUSED_FIELDS` opzione su true. Ciò eliminerà automaticamente i campi di unione che non vengono popolati durante la stampa unione, risultando in un documento più pulito.

###  Qual è la differenza tra`REMOVE_EMPTY_FIELDS` and `REMOVE_UNUSED_FIELDS` cleanup options?

 IL`REMOVE_EMPTY_FIELDS` L'opzione rimuove i campi di unione che non contengono dati o che sono vuoti durante il processo di stampa unione. D'altra parte, il`REMOVE_UNUSED_FIELDS`L'opzione rimuove i campi di unione che non vengono popolati con dati durante l'unione. La scelta tra loro dipende se si desidera rimuovere i campi senza contenuto o quelli che non sono utilizzati nella specifica operazione di unione.

### Come posso abilitare la rimozione dei paragrafi con segni di punteggiatura?

 Per abilitare la rimozione dei paragrafi con segni di punteggiatura, è possibile impostare il file`cleanupParagraphsWithPunctuationMarks` opzione su true e specificare i segni di punteggiatura da considerare per la pulizia. Ciò ti consente di creare un documento più raffinato rimuovendo i paragrafi non necessari contenenti solo punteggiatura.

### Posso personalizzare le opzioni di pulizia in Aspose.Words per Java?

Sì, puoi personalizzare le opzioni di pulizia in base alle tue esigenze specifiche. Puoi scegliere quali opzioni di pulizia applicare e configurarle secondo i requisiti di pulizia del tuo documento, assicurandoti che il tuo documento finale soddisfi gli standard desiderati.