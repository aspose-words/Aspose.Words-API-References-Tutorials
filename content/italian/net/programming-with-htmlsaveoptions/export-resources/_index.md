---
title: Esporta risorse
linktitle: Esporta risorse
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata per esportare le risorse del documento durante il salvataggio come HTML con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/export-resources/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per esportare le risorse del documento con Aspose.Words per .NET. Questa funzione consente di esportare risorse, come i caratteri, come file esterni quando si salva un documento in formato HTML.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento da esportare. Utilizzare il codice seguente per caricare il documento da una directory specificata:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Questo codice crea un'istanza di`Document` caricando il documento dalla directory specificata.

## Passaggio 3: configurazione delle opzioni di backup HTML

Ora configureremo le opzioni di salvataggio HTML per esportare le risorse del documento. Usa il seguente codice:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resources"
};
```

 Questo codice crea un'istanza di`HtmlSaveOptions` e imposta le seguenti opzioni:

- `CssStyleSheetType` è impostato per`CssStyleSheetType.External`per esportare il foglio di stile CSS in un file esterno.
- `ExportFontResources` è impostato per`true` per esportare le risorse dei caratteri.
- `ResourceFolder` specifica la directory di destinazione in cui verranno salvate le risorse.
- `ResourceFolderAlias` specifica l'alias dell'URL che verrà utilizzato per accedere alle risorse.

## Passaggio 4: conversione e salvataggio del documento in HTML

Infine, convertiremo il documento in HTML utilizzando le opzioni di salvataggio HTML configurate in precedenza. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Questo codice converte il documento in HTML e salva le risorse nella directory specificata, utilizzando l'alias URL specificato.

### Esempio di codice sorgente per Export Resources utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resources"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Assicurati di specificare il percorso corretto della directory dei documenti nel file`dataDir` variabile.