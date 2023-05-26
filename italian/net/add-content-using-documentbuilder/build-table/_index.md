---
title: Costruisci tabella
linktitle: Costruisci tabella
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare una tabella in un documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/add-content-using-documentbuilder/build-table/
---

In questo tutorial passo passo imparerai come creare una tabella in un documento Word utilizzando Aspose.Words per .NET. Ti guideremo attraverso il processo e ti forniremo i frammenti di codice C# necessari. Alla fine di questa guida, sarai in grado di creare una tabella con formattazione e contenuto personalizzati utilizzando la classe DocumentBuilder.

## Prerequisiti
Prima di iniziare, assicurati di avere i seguenti prerequisiti:
- Aspose.Words per la libreria .NET installata sul tuo sistema.

## Passaggio 1: crea un nuovo documento
Per iniziare, crea un nuovo documento utilizzando la classe Document:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: avviare il tavolo
Successivamente, usa il metodo StartTable della classe DocumentBuilder per iniziare a costruire la tabella:

```csharp
Table table = builder.StartTable();
```

## Passaggio 3: inserire celle e aggiungere contenuto
Ora puoi inserire celle nella tabella e aggiungervi contenuto utilizzando i metodi InsertCell e Write della classe DocumentBuilder. Personalizza la formattazione della cella secondo necessità:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Passaggio 4: termina la riga
Dopo aver aggiunto contenuto alle celle della prima riga, utilizzare il metodo EndRow della classe DocumentBuilder per terminare la riga:

```csharp
builder.EndRow();
```

## Passaggio 5: personalizzare la formattazione delle righe
È possibile personalizzare la formattazione di una riga impostando le proprietà degli oggetti RowFormat e CellFormat:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Passaggio 6: termina il tavolo
Per completare la tabella, utilizzare il metodo EndTable della classe DocumentBuilder:

```csharp
builder.EndTable();
```

### Esempio di codice sorgente per la creazione di una tabella utilizzando Aspose.Words per .NET
Ecco il codice sorgente completo per la creazione di una tabella utilizzando Aspose.Words per .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Conclusione
Congratulazioni! Hai imparato con successo come costruire una tabella in un documento Word usando Aspose.Words per .NET. Seguendo la guida dettagliata e utilizzando il codice sorgente fornito, ora puoi creare tabelle con formattazione personalizzata.