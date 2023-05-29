---
title: Generatore di documenti Inserisci segnalibro
linktitle: Generatore di documenti Inserisci segnalibro
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire segnalibri nei documenti di Word utilizzando DocumentBuilder in Aspose.Words per .NET. Guida passo dopo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/document-builder-insert-bookmark/
---

In questo esempio completo, imparerai come inserire segnalibri in un documento Word utilizzando la classe DocumentBuilder in Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di creare e gestire segnalibri all'interno dei tuoi documenti.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserire un segnalibro
Utilizzare quindi i metodi StartBookmark e EndBookmark della classe DocumentBuilder per inserire un segnalibro nel documento. Fornire un nome univoco per il segnalibro come parametro:

```csharp
builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");
```

## Passaggio 3: salvare il documento
Dopo aver inserito il segnalibro, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

### Esempio di codice sorgente per DocumentBuilder Inserisci segnalibro utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di un segnalibro utilizzando la classe DocumentBuilder in Aspose.Words per .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.StartBookmark("FineBookmark");
builder.Writeln("This is just a fine bookmark.");
builder.EndBookmark("FineBookmark");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.DocumentBuilderInsertBookmark.docx");
```

## Conclusione
Congratulazioni! Hai imparato con successo come inserire segnalibri in un documento di Word utilizzando la classe DocumentBuilder in Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi creare e gestire segnalibri all'interno dei tuoi documenti.

I segnalibri sono utili per vari scenari, ad esempio la navigazione in documenti di grandi dimensioni, il riferimento a sezioni specifiche o la manipolazione a livello di codice del contenuto all'interno di aree con segnalibri.

Ricorda di adattare il codice in base alle tue esigenze specifiche e di migliorarlo con funzionalità aggiuntive secondo necessità.

