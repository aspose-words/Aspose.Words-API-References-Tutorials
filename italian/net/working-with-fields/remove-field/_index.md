---
title: Rimuovi campo
linktitle: Rimuovi campo
second_title: Riferimento all'API Aspose.Words per .NET
description: In questa guida imparerai come eliminare un campo specifico in un documento utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/remove-field/
---
Ecco una guida dettagliata per spiegare il codice sorgente C# di seguito, che utilizza la funzionalità "Field Removal" di Aspose.Words per .NET. Segui attentamente ogni passaggio per ottenere i risultati desiderati.

## Passaggio 1: impostazione della directory dei documenti

Nel codice fornito, devi specificare la directory dei tuoi documenti. Sostituisci il valore "YOUR DOCUMENT DIRECTORY" con il percorso appropriato alla directory dei tuoi documenti.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Passaggio 2: caricamento del documento

Iniziamo caricando il documento esistente dal file specificato.

```csharp
Document doc = new Document(dataDir + "Various fields.docx");
```

## Passaggio 3: eliminazione del campo

 Selezioniamo il primo campo nell'intervallo del documento e utilizziamo il`Remove()` metodo per rimuoverlo.

```csharp
Field field = doc.Range.Fields[0];
field. Remove();
```

## Passaggio 4: salvare il documento

 Infine, chiamiamo il`Save()` metodo per salvare il documento modificato.

```csharp
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

### Codice sorgente di esempio per l'eliminazione del campo con Aspose.Words per .NET

```csharp
// Il percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Carica il documento.
Document doc = new Document(dataDir + "Various fields.docx");

// Selezione del campo da eliminare.
Field field = doc.Range.Fields[0];
field. Remove();

// Salva il documento.
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

Segui questi passaggi per eliminare un campo specifico nel documento utilizzando Aspose.Words per .NET.
