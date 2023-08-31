---
title: Esporta campo modulo di immissione testo come testo
linktitle: Esporta campo modulo di immissione testo come testo
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida passo passo per esportare i campi del modulo di input del testo come testo normale con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per esportare i campi del modulo di input di testo come testo normale con Aspose.Words per .NET. Questa funzione consente di esportare i campi del modulo di input del testo come testo leggibile, anziché esportarli come elementi di input HTML.

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

Ora configureremo le opzioni di salvataggio HTML per esportare i campi del modulo di input del testo come testo normale. Usa il seguente codice:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// La cartella specificata deve esistere ed essere vuota.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Questo codice crea un'istanza di`HtmlSaveOptions` imposta il`ExportTextInputFormFieldAsText` opzione a`true`per esportare i campi del modulo di input del testo come testo normale. Inoltre, specifica la cartella in cui verranno salvate le immagini estratte.

## Passaggio 4: conversione e salvataggio del documento in HTML

Infine, convertiremo il documento in HTML utilizzando le opzioni di salvataggio HTML configurate in precedenza. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Questo codice converte il documento in HTML esportando i campi del modulo di input di testo come testo normale e salva il file HTML esportato nella directory specificata.

### Esempio di codice sorgente per l'esportazione del campo del modulo di input del testo come testo utilizzando Aspose.Words per .NET


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// La cartella specificata deve esistere e deve essere vuota.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Imposta un'opzione per esportare i campi del modulo come testo normale, non come elementi di input HTML.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Assicurati di specificare il percorso corretto della directory dei documenti nel file`dataDir` variabile.