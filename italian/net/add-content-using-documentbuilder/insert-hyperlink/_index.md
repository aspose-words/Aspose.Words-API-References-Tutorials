---
title: Inserisci collegamento ipertestuale
linktitle: Inserisci collegamento ipertestuale
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire collegamenti ipertestuali nei documenti di Word utilizzando Aspose.Words per .NET Guida dettagliata.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-hyperlink/
---

In questo tutorial completo imparerai come inserire collegamenti ipertestuali in un documento di Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di aggiungere collegamenti ipertestuali cliccabili ai tuoi documenti.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserire un collegamento ipertestuale
Utilizzare quindi il metodo Write della classe DocumentBuilder per aggiungere testo e formattare il collegamento ipertestuale impostando le proprietà del colore e della sottolineatura:

```csharp
builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", falso);

builder.Font.ClearFormatting();
builder.Write(" for more information.");
```

## Passaggio 3: salvare il documento
Dopo aver inserito il collegamento ipertestuale, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

## Esempio di codice sorgente per Inserisci collegamento ipertestuale utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di un collegamento ipertestuale utilizzando Aspose.Words per .NET:

I collegamenti ipertestuali sono un modo efficace per migliorare l'interattività e l'utilità dei documenti di Word. Possono essere utilizzati per fare riferimento a risorse esterne, fornire informazioni aggiuntive o creare elementi di navigazione all'interno del documento.

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Please make sure to visit ");
	builder.Font.Color = Color.Blue;
	builder.Font.Underline = Underline.Single;
	
	builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", falso);
	
	builder.Font.ClearFormatting();
	builder.Write(" for more information.");

	doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

Ricorda di modificare il codice in base ai tuoi requisiti specifici, inclusi il testo del collegamento ipertestuale e l'URL. Miglioralo con formattazione o funzionalità aggiuntive secondo necessità.

## Conclusione
Congratulazioni! Hai imparato con successo come inserire collegamenti ipertestuali in un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata e utilizzando il codice sorgente fornito, ora puoi aggiungere collegamenti ipertestuali cliccabili ai tuoi documenti, indirizzando i lettori a siti Web esterni o URL specifici.

