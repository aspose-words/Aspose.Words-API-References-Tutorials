---
title: Inserisci Interruzione
linktitle: Inserisci Interruzione
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire interruzioni di pagina nei documenti di Word utilizzando Aspose.Words per .NET. Guida passo dopo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-break/
---

In questo esempio completo, imparerai come inserire interruzioni di pagina in un documento di Word utilizzando il metodo InsertBreak in Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di controllare le interruzioni di pagina all'interno del tuo documento.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserire contenuto e interruzioni di pagina
Utilizzare quindi il metodo Writeln della classe DocumentBuilder per aggiungere contenuto al documento. Per inserire un'interruzione di pagina, utilizzare il metodo InsertBreak con il parametro BreakType.PageBreak:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## Passaggio 3: salvare il documento
Dopo aver inserito il contenuto e le interruzioni di pagina, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### Esempio di codice sorgente per Inserisci interruzione utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di interruzioni di pagina utilizzando Aspose.Words per .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("This is page 1.");
	builder.InsertBreak(BreakType.PageBreak);

	builder.Writeln("This is page 2.");
	builder.InsertBreak(BreakType.PageBreak);

	builder.Writeln("This is page 3.");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
			
```

Ricorda di adattare il codice in base alle tue esigenze specifiche e di migliorarlo con funzionalità aggiuntive secondo necessità.


## Conclusione
Congratulazioni! Hai imparato con successo come inserire interruzioni di pagina in un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi controllare l'impaginazione e il layout del tuo documento inserendo interruzioni di pagina nelle posizioni desiderate.
