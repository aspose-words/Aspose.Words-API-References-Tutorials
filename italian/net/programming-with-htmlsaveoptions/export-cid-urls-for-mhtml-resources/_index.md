---
title: Esporta URL Cid per risorse Mhtml
linktitle: Esporta URL Cid per risorse Mhtml
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata per esportare gli URL CID delle risorse MHTML durante il salvataggio di un documento con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per esportare gli URL CID per le risorse MHTML con Aspose.Words per .NET. Questa funzione consente di esportare gli URL CID delle risorse MHTML quando si salva un documento in formato MHTML.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento da esportare. Utilizzare il codice seguente per caricare il documento da una directory specificata:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Questo codice crea un'istanza di`Document` caricando il documento dalla directory specificata.

## Passaggio 3: configurazione delle opzioni di backup HTML

Ora configureremo le opzioni di salvataggio HTML per esportare gli URL CID delle risorse MHTML. Usa il seguente codice:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Questo codice crea un'istanza di`HtmlSaveOptions` con il formato di salvataggio impostato su MHTML. Consente inoltre l'esportazione di URL CID di risorse MHTML tramite l'impostazione`ExportCidUrlsForMhtmlResources` A`true`.

## Passaggio 4: conversione e salvataggio del documento in MHTML

Infine, convertiremo il documento in MHTML utilizzando le opzioni di salvataggio HTML configurate in precedenza. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Questo codice converte il documento in MHTML e lo salva in un file con gli URL CID delle risorse MHTML esportate.

### Codice sorgente di esempio per l'esportazione di URL Cid per risorse Mhtml utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Assicurati di specificare il percorso corretto della directory dei documenti nel file`dataDir` variabile.

Ora hai imparato come esportare gli URL CID delle risorse MHTML durante il salvataggio di un documento in formato MHTML utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi gestire facilmente gli URL CID nei tuoi documenti MHTML esportati.

