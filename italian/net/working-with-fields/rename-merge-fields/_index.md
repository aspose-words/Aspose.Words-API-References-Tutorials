---
title: Rinomina campi di unione
linktitle: Rinomina campi di unione
second_title: Riferimento all'API Aspose.Words per .NET
description: In questo tutorial imparerai come rinominare i campi di unione in un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/rename-merge-fields/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito che utilizza la funzionalità di ridenominazione dei campi di unione di Aspose.Words per .NET. Segui attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: creazione del documento e inserimento dei campi di unione

 Iniziamo creando un nuovo documento e utilizzando a`DocumentBuilder` per inserire i campi di unione.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Passaggio 3: ridenominazione dei campi di unione

Esaminiamo ogni campo nell'intervallo del documento e, se si tratta di un campo di unione, rinominiamo il campo aggiungendo "_Suffisso "rinominato".

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Passaggio 4: salvare il documento

 Infine, chiamiamo il`Save()` metodo per salvare il documento modificato.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Esempio di codice sorgente per rinominare i campi di unione con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Creare il documento e inserire i campi di unione.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Rinominare i campi di unione.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Salva il documento.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Segui questi passaggi per rinominare i campi di unione nel documento utilizzando Aspose.Words per .NET.