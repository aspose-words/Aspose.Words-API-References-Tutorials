---
title: Rinominare i campi unione
linktitle: Rinominare i campi unione
second_title: API di elaborazione dei documenti Aspose.Words
description: In questo tutorial imparerai come rinominare i campi di unione in un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/rename-merge-fields/
---

Ecco una guida passo passo per spiegare il codice sorgente C# di seguito che utilizza la funzionalità di ridenominazione dei campi di unione di Aspose.Words per .NET. Segui attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "LA TUA DIRECTORY DOCUMENTI" con il percorso appropriato della directory dei tuoi documenti.

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

## Passaggio 3: rinominare i campi unione

Esaminiamo ogni campo nell'intervallo del documento e, se si tratta di un campo di unione, rinominiamo il campo aggiungendo il "_Suffisso "rinominato".

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

## Passaggio 4: salvataggio del documento

 Infine, chiamiamo il`Save()` metodo per salvare il documento modificato.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Esempio di codice sorgente per rinominare i campi di unione con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Crea il documento e inserisci i campi di unione.
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

### Domande frequenti

#### D: Come posso rinominare i campi uniti in un documento Word utilizzando Aspose.Words per .NET?

 R: Per rinominare i campi uniti in un documento Word utilizzando Aspose.Words per .NET, è possibile scorrere i campi nel documento utilizzando il comando`FieldMergingArgs` classe e utilizzare il file`FieldMergingArgs.FieldName` metodo per rinominare il campo.

#### D: È possibile rinominare solo alcuni campi uniti in un documento Word con Aspose.Words per .NET?

R: Sì, è possibile rinominare solo alcuni campi uniti in un documento Word con Aspose.Words per .NET. Puoi filtrare quali campi rinominare utilizzando criteri specifici, come il nome del campo o altre proprietà pertinenti. Quindi puoi rinominare i campi corrispondenti utilizzando il file`FieldMergingArgs.FieldName` metodo.

#### D: Come posso verificare se un campo unito è stato rinominato correttamente in un documento Word con Aspose.Words per .NET?

 R: Per verificare se un campo unito è stato rinominato con successo in un documento Word con Aspose.Words per .NET, puoi utilizzare il comando`FieldMergedArgs` classe e accedi al`FieldMergedArgs.IsMerged` proprietà per determinare se il campo è stato rinominato con hit.

#### D: Quali sono le conseguenze della ridenominazione di un campo unito in un documento di Word con Aspose.Words per .NET?

R: Quando si rinomina un campo unito in un documento di Word con Aspose.Words per .NET, cambia il nome del campo nel documento, che potrebbe influire su altre funzionalità o processi che dipendono dal nome del campo. Assicurati di considerare queste potenziali conseguenze prima di rinominare i campi uniti.

#### D: È possibile ripristinare il nome originale di un campo unito dopo averlo rinominato con Aspose.Words per .NET?

R: Sì, è possibile ripristinare il nome originale di un campo unito dopo averlo rinominato con Aspose.Words per .NET. Puoi memorizzare il nome originale del campo in una variabile o in un elenco e quindi utilizzare tali informazioni per ripristinare il nome originale, se necessario.