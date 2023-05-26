---
title: Impostare l'impostazione della pagina e la formattazione della sezione
linktitle: Impostare l'impostazione della pagina e la formattazione della sezione
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per impostare il layout di un documento e la formattazione della sezione con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per impostare il layout e la formattazione della sezione con Aspose.Words per .NET. Questa funzione consente di impostare l'orientamento della pagina, i margini e il formato della carta.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: creazione del documento

In questo passaggio, creeremo un nuovo documento. Utilizzare il codice seguente per creare il documento e inizializzare il costruttore:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si desidera salvare il documento.

## Passaggio 3: impostazione del layout e salvataggio del documento

Ora configuriamo il layout del documento. Utilizzare il codice seguente per impostare l'orientamento, i margini e il formato della carta:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Questo codice imposterà l'orientamento della pagina su orizzontale, il margine sinistro su 50 e il formato carta su 10x14.

### Codice sorgente di esempio per l'impostazione dell'impostazione della pagina e la formattazione della sezione utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

Assicurarsi di specificare il percorso corretto della directory in cui si desidera salvare il documento nel file`dataDir` variabile.

Ora hai imparato come configurare il layout e la formattazione della sezione di un documento utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi facilmente personalizzare il layout e la formattazione dei tuoi documenti.