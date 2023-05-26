---
title: Converti metafile in Svg
linktitle: Converti metafile in Svg
second_title: Riferimento all'API Aspose.Words per .NET
description: Guida dettagliata alla conversione di metafile in formato SVG durante la conversione di un documento in HTML con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per convertire i metafile in formato SVG con Aspose.Words per .NET. Questa funzione consente di convertire i metafile in formato SVG durante la conversione di un documento in HTML.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: Inserimento di un'immagine SVG nel documento

In questo passaggio, inseriremo un'immagine SVG nel documento da convertire. Utilizza il seguente codice per inserire un'immagine SVG utilizzando un tag HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Questo codice crea un'istanza di`Document` E`DocumentBuilder` per costruire il documento. Inserisce un`<svg>` tag contenente un`<polygon>` elemento con attributi per definire la forma e lo stile dell'immagine SVG.

## Passaggio 3: imposta le opzioni di salvataggio HTML

Ora imposteremo le opzioni di salvataggio HTML, specificando che i metafile devono essere convertiti in formato SVG. Usa il seguente codice:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Questo codice crea un'istanza di`HtmlSaveOptions` e set`MetafileFormat` A`HtmlMetafileFormat.Svg` per specificare che i metafile devono essere convertiti in formato SVG durante la conversione in HTML.

## Passaggio 4: conversione e salvataggio del documento in HTML

Infine, convertiremo il documento in HTML utilizzando le opzioni di salvataggio HTML definite in precedenza. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Questo codice converte il documento in HTML e lo salva in un file con i metafile convertiti in SVG.

### Codice sorgente di esempio per Converti metafile in Svg utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
