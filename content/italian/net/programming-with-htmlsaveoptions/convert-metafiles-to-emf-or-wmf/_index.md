---
title: Converti metafile in Emf o Wmf
linktitle: Converti metafile in Emf o Wmf
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per convertire i metafile nei formati EMF o WMF durante la conversione di un documento in HTML con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

In questo tutorial ti guideremo attraverso il codice sorgente C# per convertire i metafile in formato EMF o WMF con Aspose.Words per .NET. Questa funzione consente di convertire le immagini in formato metafile in formati più compatibili come EMF o WMF durante la conversione di un documento in HTML.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurati che nel tuo progetto venga fatto riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: inserimento di un'immagine nel documento

In questo passaggio inseriremo un'immagine nel documento da convertire. Utilizza il codice seguente per inserire un'immagine da un'origine dati utilizzando un tag HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Questo codice crea un'istanza di`Document` E`DocumentBuilder` per costruire il documento. Inserisce un`<img>` tag nel documento con un'immagine codificata base64.

## Passaggio 3: imposta le opzioni di salvataggio HTML

Ora imposteremo le opzioni di salvataggio HTML, incluso il formato metafile da utilizzare per le immagini. Utilizza il seguente codice:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Questo codice crea un'istanza di`HtmlSaveOptions` e imposta`MetafileFormat` A`HtmlMetafileFormat.EmfOrWmf` per specificare che i metafile devono essere convertiti nel formato EMF o WMF durante la conversione in HTML.

## Passaggio 4: convertire e salvare il documento in HTML

Infine convertiremo il documento in HTML utilizzando le opzioni di salvataggio HTML precedentemente definite. Utilizza il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Questo codice converte il documento in HTML e lo salva in un file con i metafile convertiti in formato EMF o WMF a seconda delle opzioni di salvataggio impostate.

### Codice sorgente di esempio per convertire metafile in Emf o Wmf utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Assicurati di specificare il percorso corretto della directory dei documenti nel file`dataDir` variabile.

Ora hai imparato come convertire i metafile nei formati EMF o WMF durante la conversione di un documento in HTML utilizzando Aspose.Words per .NET. Seguendo la guida passo passo fornita in questo tutorial, puoi gestire facilmente i metafile nei tuoi documenti HTML convertiti.