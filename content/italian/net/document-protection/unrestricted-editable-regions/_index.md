---
title: Aree modificabili illimitate nel documento Word
linktitle: Aree modificabili illimitate nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come creare aree modificabili senza restrizioni in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/document-protection/unrestricted-editable-regions/
---
In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità delle aree modificabili senza restrizioni di Aspose.Words per .NET. Questa funzionalità consente di definire aree in un documento di Word in cui il contenuto può essere modificato senza restrizioni, anche se il resto del documento è di sola lettura. Seguire i passaggi seguenti:

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
// Viene creato un oggetto EditableRange per EditableRangeStart appena creato.
EditableRange editableRange = edRangeStart.EditableRange;

// Inserisci qualcosa all'interno dell'intervallo modificabile.
builder.Writeln("Paragraph inside first editable range");

// Un intervallo modificabile è ben formato se ha un inizio e una fine.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Passaggio 3: aggiungi contenuti al di fuori delle aree modificabili

Puoi aggiungere contenuti al di fuori delle aree modificabili, che rimarranno di sola lettura:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Passaggio 4: salva il documento

Infine, salva il documento modificato:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Assicurati di specificare il percorso e il nome file corretti per salvare il documento con aree modificabili.

### Codice sorgente di esempio per regioni modificabili senza restrizioni utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per le aree modificabili senza restrizioni utilizzando Aspose.Words per .NET:

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
// Viene creato un oggetto EditableRange per EditableRangeStart appena creato.
EditableRange editableRange = edRangeStart.EditableRange;

// Inserisci qualcosa all'interno dell'intervallo modificabile.
builder.Writeln("Paragraph inside first editable range");

// Un intervallo modificabile è ben formato se ha un inizio e una fine.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Seguendo questi passaggi, puoi facilmente creare aree modificabili senza restrizioni nel tuo documento Word con Aspose.Words per .NET.

## Conclusione
In questo tutorial, abbiamo imparato come creare aree modificabili senza restrizioni in un documento Word utilizzando Aspose.Words per .NET. Seguendo i passaggi forniti, puoi definire aree specifiche all'interno del documento in cui gli utenti possono modificare liberamente il contenuto mantenendo il resto del documento di sola lettura. Aspose.Words per .NET offre potenti funzionalità per la protezione e la personalizzazione dei documenti, fornendoti il controllo sulle capacità di modifica dei tuoi documenti Word.

### Domande frequenti sulle aree modificabili senza restrizioni nel documento Word

#### D: Quali sono le aree modificabili senza restrizioni in Aspose.Words per .NET?

R: Le aree modificabili senza restrizioni in Aspose.Words per .NET sono aree all'interno di un documento Word in cui il contenuto può essere modificato senza alcuna restrizione, anche se il resto del documento è impostato come di sola lettura. Queste aree forniscono un modo per definire parti specifiche del documento che gli utenti possono modificare mantenendo la protezione generale del documento.

#### D: Come posso creare regioni modificabili senza restrizioni utilizzando Aspose.Words per .NET?

R: Per creare aree modificabili senza restrizioni in un documento Word utilizzando Aspose.Words per .NET, puoi seguire questi passaggi:
1.  Caricare il documento esistente utilizzando il file`Document` classe.
2.  Imposta la protezione del documento su sola lettura utilizzando il file`Protect` metodo del`Document` oggetto.
3.  Usa il`DocumentBuilder` classe per creare un intervallo modificabile aggiungendo un file`EditableRangeStart` oggetto e un`EditableRangeEnd` oggetto.
4.  Aggiungi contenuto all'interno dell'intervallo modificabile utilizzando il file`DocumentBuilder`.
5.  Salvare il documento modificato utilizzando il file`Save` metodo del`Document` oggetto.

#### D: Posso avere più aree modificabili senza restrizioni in un documento Word?

R: Sì, puoi avere più aree modificabili senza restrizioni in un documento Word. Per raggiungere questo obiettivo, è possibile creare più set di`EditableRangeStart` E`EditableRangeEnd` oggetti utilizzando il`DocumentBuilder` classe. Ogni set di oggetti definirà un'area modificabile separata in cui gli utenti potranno modificare il contenuto senza alcuna restrizione.

#### D: Posso annidare regioni modificabili l'una nell'altra?

 R: No, non è possibile annidare regioni modificabili l'una nell'altra utilizzando Aspose.Words per .NET. Ciascuna regione modificabile definita da un`EditableRangeStart` E`EditableRangeEnd` la coppia deve essere indipendente e non sovrapporsi o essere nidificata all'interno di un'altra regione modificabile. Le aree modificabili nidificate non sono supportate.

#### D: Posso rimuovere la protezione di sola lettura dal documento all'interno di un'area modificabile?

R: No, non è possibile rimuovere la protezione di sola lettura dal documento all'interno di un'area modificabile. La protezione di sola lettura viene applicata all'intero documento e non può essere rimossa selettivamente all'interno di specifiche aree modificabili. Lo scopo delle aree modificabili è consentire la modifica del contenuto mantenendo il documento complessivo di sola lettura.