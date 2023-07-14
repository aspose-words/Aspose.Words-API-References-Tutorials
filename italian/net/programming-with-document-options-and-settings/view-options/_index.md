---
title: Visualizza opzioni
linktitle: Visualizza opzioni
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata per configurare le opzioni di visualizzazione dei documenti con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-options-and-settings/view-options/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per configurare le opzioni di visualizzazione con Aspose.Words per .NET. Questa funzione consente di personalizzare la modalità di visualizzazione e il livello di zoom in un documento.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento Word per il quale vogliamo configurare le opzioni di visualizzazione. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: configurazione delle opzioni di visualizzazione

Ora configureremo le opzioni di visualizzazione del documento. Utilizzare il seguente codice per impostare la modalità di visualizzazione e il livello di zoom:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Questo codice imposta la modalità di visualizzazione su "PageLayout" e il livello di zoom su 50%.

### Codice sorgente di esempio per le opzioni di visualizzazione utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Assicurarsi di specificare il percorso del documento corretto nel file`dataDir` variabile.

Ora hai imparato come configurare le opzioni di visualizzazione dei documenti utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi facilmente personalizzare la visualizzazione dei tuoi documenti.