---
title: Converti metafile in Svg
linktitle: Converti metafile in Svg
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per convertire i metafile in formato SVG durante la conversione di un documento in HTML con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

In questo tutorial ti guideremo attraverso il codice sorgente C# per convertire i metafile in formato SVG con Aspose.Words per .NET. Questa funzionalità ti consente di convertire i metafile nel formato SVG durante la conversione di un documento in HTML.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurati che nel tuo progetto venga fatto riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: inserimento di un'immagine SVG nel documento

In questo passaggio inseriremo un'immagine SVG nel documento da convertire. Utilizza il codice seguente per inserire un'immagine SVG utilizzando un tag HTML:

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

 Questo codice crea un'istanza di`Document` E`DocumentBuilder` per costruire il documento. Inserisce a`<svg>` tag contenente a`<polygon>` elemento con attributi per definire la forma e lo stile dell'immagine SVG.

## Passaggio 3: imposta le opzioni di salvataggio HTML

Ora imposteremo le opzioni di salvataggio HTML, specificando che i metafile devono essere convertiti nel formato SVG. Utilizza il seguente codice:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Questo codice crea un'istanza di`HtmlSaveOptions` e imposta`MetafileFormat` A`HtmlMetafileFormat.Svg` per specificare che i metafile devono essere convertiti nel formato SVG durante la conversione in HTML.

## Passaggio 4: convertire e salvare il documento in HTML

Infine, convertiremo il documento in HTML utilizzando le opzioni di salvataggio HTML definite in precedenza. Utilizza il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Questo codice converte il documento in HTML e lo salva in un file con i metafile convertiti in SVG.

### Codice sorgente di esempio per Convertire metafile in Svg utilizzando Aspose.Words per .NET

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
