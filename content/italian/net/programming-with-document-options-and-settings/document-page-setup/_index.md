---
title: Impostazione pagina documento
linktitle: Impostazione pagina documento
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per impostare un layout di documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-document-options-and-settings/document-page-setup/
---

In questo tutorial ti guideremo attraverso il codice sorgente C# per configurare il layout del documento con Aspose.Words per .NET. Questa funzione consente di impostare la modalità di layout, il numero di caratteri per riga e il numero di righe per pagina.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurati che nel tuo progetto venga fatto riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio caricheremo il documento Word che vogliamo configurare. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: impostazione del layout

Ora configuriamo il layout del documento. Utilizzare il codice seguente per impostare la modalità di layout, il numero di caratteri per riga e il numero di righe per pagina:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Questo codice imposta la modalità di layout su "Griglia" e quindi specifica il numero di caratteri per riga e il numero di righe per pagina.

### Codice sorgente di esempio per l'impostazione della pagina del documento utilizzando Aspose.Words per .NET


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Imposta la modalità di layout per una sezione consentendo di definire il comportamento della griglia del documento.
	// Tieni presente che la scheda Griglia documento diventa visibile nella finestra di dialogo Imposta pagina di MS Word.
	// se una qualsiasi lingua asiatica è definita come lingua di modifica.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Assicurati di specificare il percorso corretto del documento nel file`dataDir` variabile.

Ora hai imparato come configurare il layout di un documento utilizzando Aspose.Words per .NET. Seguendo la guida passo passo fornita in questo tutorial, puoi personalizzare facilmente il layout dei tuoi documenti.