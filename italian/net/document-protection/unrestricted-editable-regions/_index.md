---
title: Regioni modificabili illimitate
linktitle: Regioni modificabili illimitate
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare aree modificabili illimitate in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-protection/unrestricted-editable-regions/
---

In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di aree modificabili illimitate di Aspose.Words per .NET. Questa funzione consente di definire aree in un documento Word in cui il contenuto può essere modificato senza restrizioni, anche se il resto del documento è di sola lettura. Segui i passaggi seguenti:

## Passaggio 1: caricamento del documento e impostazione della protezione

Inizia caricando il documento esistente:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Proteggi il documento impostando il tipo di protezione e la password di sola lettura

## Passaggio 2: creazione di un'area modificabile

Inizia creando un'area modificabile utilizzando gli oggetti EditableRangeStart e EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Viene creato un oggetto EditableRange per l'EditableRangeStart che abbiamo appena creato.
EditableRange editableRange = edRangeStart.EditableRange;

// Metti qualcosa all'interno dell'intervallo modificabile.
builder.Writeln("Paragraph inside first editable range");

// Un intervallo modificabile è ben formato se ha un inizio e una fine.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Passaggio 3: aggiungi contenuti al di fuori delle aree modificabili

Puoi aggiungere contenuti al di fuori delle aree modificabili, che rimarranno di sola lettura:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Passaggio 4: salvare il documento

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Assicurati di specificare il percorso e il nome file corretti per salvare il documento con aree modificabili.

### Codice sorgente di esempio per aree modificabili illimitate utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per aree modificabili illimitate utilizzando Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Carica un documento e rendilo di sola lettura.
	Document doc = new Document(MyDir + "Document.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	doc.Protect(ProtectionType.ReadOnly, "MyPassword");

	builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

	// Inizia un intervallo modificabile.
	EditableRangeStart edRangeStart = builder.StartEditableRange();
	// Viene creato un oggetto EditableRange per l'EditableRangeStart che abbiamo appena creato.
	EditableRange editableRange = edRangeStart.EditableRange;

	// Metti qualcosa all'interno dell'intervallo modificabile.
	builder.Writeln("Paragraph inside first editable range");

	// Un intervallo modificabile è ben formato se ha un inizio e una fine.
	EditableRangeEnd edRangeEnd = builder.EndEditableRange();

	builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

	doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Seguendo questi passaggi, puoi facilmente creare aree modificabili illimitate nel tuo documento Word con Aspose.Words per .NET.


