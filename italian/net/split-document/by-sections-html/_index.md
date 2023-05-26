---
title: Per sezioni Html
linktitle: Per sezioni Html
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come suddividere un documento Word in sezioni Html utilizzando Aspose.Words per .NET con un esempio di codice completo.
type: docs
weight: 10
url: /it/net/split-document/by-sections-html/
---

In questo esempio, ti mostreremo come suddividere un documento Word in sezioni separate in formato HTML utilizzando la funzione Per sezioni HTML di Aspose.Words per .NET. Segui i passaggi seguenti per comprendere il codice sorgente e generare documenti HTML separati per ogni sezione.

## Passaggio 1: caricamento del documento

Per iniziare, specifica la directory per il tuo documento e carica il documento in un oggetto Document. Ecco come:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Passaggio 2: divisione del documento in sezioni in formato HTML

Ora imposteremo le opzioni di salvataggio per dividere il documento in sezioni in formato HTML. Ecco come farlo:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Codice sorgente di esempio per HTML per sezioni utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per la funzione Per sezioni HTML di Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Rendering.docx");

	
	HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };
	
	
	doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);

```

Con questo codice sarai in grado di dividere un documento Word in sezioni separate in formato HTML usando Aspose.Words per .NET.

Ora puoi generare documenti HTML separati per ogni sezione del documento iniziale.



