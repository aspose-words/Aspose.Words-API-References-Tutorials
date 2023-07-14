---
title: Inserisci Html
linktitle: Inserisci Html
second_title: Aspose.Words API di elaborazione dei documenti
description: Scopri come inserire contenuto HTML nei documenti di Word utilizzando Aspose.Words per .NET. Guida passo dopo passo.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-html/
---

In questo tutorial completo imparerai come inserire contenuto HTML in un documento Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di aggiungere elementi HTML, formattazione e stili ai tuoi documenti Word.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: inserire il contenuto HTML
Utilizzare quindi il metodo InsertHtml della classe DocumentBuilder per inserire contenuto HTML nel documento. Puoi includere tag, attributi e stili HTML all'interno della stringa HTML:

```csharp
builder.InsertHtml(
	"<P align='right'>Paragraph right</P>" +
	"<b>Implicit paragraph left</b>" +
	"<div align='center'>Div center</div>" +
	"<h1 align='left'>Heading 1 left.</h1>");
```

## Passaggio 3: salvare il documento
Dopo aver inserito il contenuto HTML, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
```

## Esempio di codice sorgente per Inserisci HTML utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di contenuto HTML in un documento Word utilizzando Aspose.Words per .NET:
Questa funzione è particolarmente utile quando si dispone di contenuto HTML esistente che si desidera includere nei documenti di Word preservando la formattazione e il layout originali.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertHtml(
	"<P align='right'>Paragraph right</P>" +
	"<b>Implicit paragraph left</b>" +
	"<div align='center'>Div center</div>" +
	"<h1 align='left'>Heading 1 left.</h1>");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHtml.docx");
```

Ricorda di modificare il codice in base ai tuoi requisiti e contenuti HTML specifici. Assicurati che il tuo codice HTML sia ben formato e compatibile con Aspose.Words per .NET.

## Conclusione
Congratulazioni! Hai imparato con successo come inserire contenuto HTML in un documento Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi incorporare elementi HTML, formattazione e stili nei tuoi documenti Word.


