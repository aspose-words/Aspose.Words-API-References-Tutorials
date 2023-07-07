---
title: Confronta le opzioni
linktitle: Confronta le opzioni
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per spiegare il codice sorgente C# della funzione Confronta opzioni con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/compare-documents/compare-options/
---

In questo tutorial, spiegheremo come utilizzare la funzione Confronta opzioni con Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e applicare le modifiche.

## Passaggio 1: confronta i documenti con le opzioni personalizzate

 Per iniziare, carica due documenti da confrontare. In questo esempio, useremo il`Clone()` metodo per creare una copia del documento originale. Ecco come:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Passaggio 2: configurazione delle opzioni di confronto

 Ora configureremo le opzioni di confronto creando un file`CompareOptions` oggetto e impostando le varie proprietà secondo necessità. Ecco come:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Passaggio 3: confronta i documenti con le opzioni personalizzate

 Useremo ora il`Compare()` metodo passando le opzioni personalizzate per confrontare i due documenti. Questo metodo segnerà le modifiche nel documento originale. Ecco come:

```csharp
// Confronta documenti con opzioni personalizzate
docA.Compare(docB, "user", DateTime.Now, options);

// Controlla se i documenti sono uguali
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Codice sorgente di esempio per Opzioni di confronto utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Confronta opzioni con Aspose.Words per .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Con questo codice puoi confrontare due documenti utilizzando opzioni personalizzate per ignorare elementi specifici durante il confronto con Aspose.Words per .NET.

