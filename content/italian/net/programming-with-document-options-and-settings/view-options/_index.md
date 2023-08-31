---
title: Visualizza opzioni
linktitle: Visualizza opzioni
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per configurare le opzioni di visualizzazione dei documenti con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-options-and-settings/view-options/
---

In questo tutorial ti guideremo attraverso il codice sorgente C# per configurare le opzioni di visualizzazione con Aspose.Words per .NET. Questa funzione consente di personalizzare la modalità di visualizzazione e il livello di zoom in un documento.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurati che nel tuo progetto venga fatto riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio caricheremo il documento Word per il quale vogliamo configurare le opzioni di visualizzazione. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: configurazione delle opzioni di visualizzazione

Ora configureremo le opzioni di visualizzazione del documento. Utilizzare il codice seguente per impostare la modalità di visualizzazione e il livello di zoom:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Questo codice imposta la modalità di visualizzazione su "PageLayout" e il livello di zoom al 50%.

### Codice sorgente di esempio per Opzioni di visualizzazione utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Assicurati di specificare il percorso corretto del documento nel file`dataDir` variabile.

Ora hai imparato come configurare le opzioni di visualizzazione del documento utilizzando Aspose.Words per .NET. Seguendo la guida passo passo fornita in questo tutorial, puoi personalizzare facilmente la visualizzazione dei tuoi documenti.