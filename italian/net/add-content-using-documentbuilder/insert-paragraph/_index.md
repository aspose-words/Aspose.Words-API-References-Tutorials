---
title: Inserisci paragrafo
linktitle: Inserisci paragrafo
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come inserire paragrafi formattati nei documenti di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/insert-paragraph/
---

In questo tutorial completo imparerai come inserire paragrafi in un documento Word usando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di aggiungere paragrafi formattati ai tuoi documenti.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: creare un nuovo documento e DocumentBuilder
Per iniziare, crea un nuovo documento utilizzando la classe Document e inizializza un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: imposta il carattere e la formattazione
Successivamente, imposta le proprietà del carattere e la formattazione del paragrafo utilizzando rispettivamente gli oggetti Font e ParagraphFormat:

```csharp
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;
```

## Passaggio 3: inserire un paragrafo
Dopo aver impostato il carattere e la formattazione, utilizzare il metodo Writeln della classe DocumentBuilder per inserire un intero paragrafo:

```csharp
builder.Writeln("A whole paragraph.");
```

## Passaggio 4: salvare il documento
Dopo aver inserito il paragrafo, salvare il documento in un file utilizzando il metodo Save della classe Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## Esempio di codice sorgente per Inserisci paragrafo utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per l'inserimento di un paragrafo utilizzando Aspose.Words per .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.FirstLineIndent = 8;
paragraphFormat.Alignment = ParagraphAlignment.Justify;
paragraphFormat.KeepTogether = true;

builder.Writeln("A whole paragraph.");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
```

## Conclusione
Congratulazioni! Hai imparato con successo come inserire paragrafi formattati in un documento di Word utilizzando Aspose.Words per .NET. Seguendo la guida passo passo e utilizzando il codice sorgente fornito, ora puoi aggiungere paragrafi personalizzati con caratteri, formattazione e allineamento specifici ai tuoi documenti.