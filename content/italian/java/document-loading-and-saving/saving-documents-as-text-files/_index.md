---
title: Salvataggio di documenti come file di testo in Aspose.Words per Java
linktitle: Salvataggio di documenti come file di testo
second_title: API di elaborazione dei documenti Java Aspose.Words
description: Scopri come salvare documenti come file di testo in Aspose.Words per Java. Segui la nostra guida passo passo con esempi di codice Java.
type: docs
weight: 24
url: /it/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Introduzione al salvataggio di documenti come file di testo in Aspose.Words per Java

In questo tutorial esploreremo come salvare documenti come file di testo utilizzando la libreria Aspose.Words per Java. Aspose.Words è una potente API Java per lavorare con documenti Word e fornisce varie opzioni per salvare documenti in diversi formati, incluso il testo semplice. Tratteremo i passaggi per raggiungere questo obiettivo e forniremo codice Java di esempio lungo il percorso.

## Prerequisiti

Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:

- Java Development Kit (JDK) installato sul tuo sistema.
-  Libreria Aspose.Words per Java integrata nel tuo progetto. Puoi scaricarlo da[Qui](https://releases.aspose.com/words/java/).
- Conoscenza base della programmazione Java.

## Passaggio 1: crea un documento

Per salvare un documento come file di testo, dobbiamo prima creare un documento utilizzando Aspose.Words. Ecco un semplice snippet di codice Java per creare un documento con alcuni contenuti:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

In questo codice creiamo un nuovo documento e vi aggiungiamo del testo, incluso testo in diverse lingue.

## Passaggio 2: definire le opzioni di salvataggio del testo

Successivamente, dobbiamo definire le opzioni di salvataggio del testo che specificano come il documento deve essere salvato come file di testo. Possiamo configurare varie impostazioni come l'aggiunta di contrassegni bidi, il rientro dell'elenco e altro. Vediamo due esempi:

### Esempio 1: aggiunta di segni Bidi

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 In questo esempio creiamo un file`TxtSaveOptions` oggetto e impostare il`AddBidiMarks`proprietà a`true` per includere i segni bidi nell'output del testo.

### Esempio 2: utilizzo del carattere di tabulazione per il rientro dell'elenco

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

Qui configuriamo le opzioni di salvataggio per utilizzare un carattere di tabulazione per il rientro dell'elenco con un conteggio pari a 1.

## Passaggio 3: salva il documento come testo

Ora che abbiamo definito le opzioni di salvataggio del testo, possiamo salvare il documento come file di testo. Il codice seguente illustra come eseguire questa operazione:

```java
doc.save("output.txt", saveOptions);
```

 Sostituire`"output.txt"` con il percorso del file desiderato in cui si desidera salvare il file di testo.

## Codice sorgente completo per salvare documenti come file di testo in Aspose.Words per Java

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Crea un elenco con tre livelli di rientro.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Crea un elenco con tre livelli di rientro.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## Conclusione

In questo tutorial, abbiamo imparato come salvare documenti come file di testo in Aspose.Words per Java. Abbiamo coperto i passaggi per creare un documento, definire le opzioni di salvataggio del testo e salvare il documento in formato testo. Aspose.Words offre un'ampia flessibilità quando si tratta di salvare documenti, consentendoti di personalizzare l'output in base alle tue esigenze specifiche.

## Domande frequenti

### Come posso aggiungere segni Bidi all'output del testo?

 Per aggiungere segni bidi all'output testuale, impostare il file`AddBidiMarks` proprietà di`TxtSaveOptions` A`true`. Per esempio:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### Posso personalizzare il carattere del rientro dell'elenco?

 Sì, puoi personalizzare il carattere di rientro dell'elenco configurando il file`ListIndentation` proprietà di`TxtSaveOptions`. Ad esempio, per utilizzare un carattere di tabulazione per il rientro dell'elenco, puoi procedere come segue:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### Aspose.Words per Java è adatto alla gestione di testo multilingue?

Sì, Aspose.Words per Java è adatto per gestire testo multilingue. Supporta varie lingue e codifiche di caratteri, rendendolo una scelta versatile per lavorare con documenti in diverse lingue.

### Come posso accedere a più documentazione e risorse per Aspose.Words per Java?

 È possibile trovare documentazione e risorse complete per Aspose.Words per Java sul sito Web della documentazione di Aspose:[Aspose.Words per la documentazione Java](https://reference.aspose.com/words/java/).

### Dove posso scaricare Aspose.Words per Java?

 È possibile scaricare la libreria Aspose.Words per Java dal sito Web Aspose:[Scarica Aspose.Words per Java](https://releases.aspose.com/words/java/).