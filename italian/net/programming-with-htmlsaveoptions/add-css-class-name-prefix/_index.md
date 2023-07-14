---
title: Aggiungi il prefisso del nome della classe CSS
linktitle: Aggiungi il prefisso del nome della classe CSS
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata per aggiungere un prefisso del nome di una classe CSS durante la conversione di un documento in HTML con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

In questo tutorial, ti guideremo attraverso il codice sorgente C# per aggiungere un prefisso del nome di una classe CSS con Aspose.Words per .NET. Questa funzione consente di aggiungere un prefisso personalizzato ai nomi delle classi CSS generate durante la conversione di un documento in HTML.

## Passaggio 1: impostazione del progetto

Per iniziare, crea un nuovo progetto C# nel tuo IDE preferito. Assicurarsi che nel progetto si faccia riferimento alla libreria Aspose.Words per .NET.

## Passaggio 2: caricamento del documento

In questo passaggio, caricheremo il documento Word che vogliamo convertire in HTML. Utilizzare il seguente codice per caricare il documento:

```csharp
// Percorso della directory dei documenti.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Sostituire`"YOUR DOCUMENTS DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

## Passaggio 3: imposta le opzioni di salvataggio HTML

Ora impostiamo le opzioni di salvataggio HTML, incluso il tipo di foglio di stile CSS e il prefisso del nome della classe CSS. Usa il seguente codice:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Questo codice crea un'istanza di`HtmlSaveOptions` e set`CssStyleSheetType` A`CssStyleSheetType.External` per generare un foglio di stile CSS esterno, e`CssClassNamePrefix` A`"pfx_"`prefisso`"pfx_"` ai nomi delle classi CSS.

## Passaggio 4: conversione e salvataggio del documento in HTML

Infine, convertiremo il documento in HTML utilizzando le opzioni di salvataggio HTML definite in precedenza. Usa il seguente codice:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Questo codice converte il documento in HTML e lo salva in un file con l'aggiunta del prefisso del nome della classe CSS.

### Codice sorgente di esempio per aggiungere il prefisso del nome della classe Css utilizzando Aspose.Words per .NET

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Assicurarsi di specificare il percorso del documento corretto nel file`dataDir` variabile.

Ora hai imparato come aggiungere un prefisso al nome di una classe CSS durante la conversione di un documento in HTML utilizzando Aspose.Words per .NET. Seguendo la guida dettagliata fornita in questo tutorial, puoi personalizzare i nomi delle classi CSS nei tuoi documenti HTML convertiti.