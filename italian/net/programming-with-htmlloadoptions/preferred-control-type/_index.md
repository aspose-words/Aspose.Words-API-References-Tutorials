---
title: Tipo di controllo preferito
linktitle: Tipo di controllo preferito
second_title: Aspose.Words API di elaborazione dei documenti
description: Guida dettagliata per specificare il tipo di controllo preferito durante il caricamento di un documento HTML con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlloadoptions/preferred-control-type/
---

Questo articolo fornisce una guida dettagliata su come utilizzare la funzionalità del tipo di controllo preferito con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial, sarai in grado di capire come specificare il tipo di controllo preferito durante il caricamento di un documento HTML.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. Puoi trovare la libreria e le istruzioni di installazione sul sito web di Aspose.

## Passaggio 1: definire il codice HTML

 Per iniziare, devi definire il codice HTML che desideri caricare come documento. In questo esempio, abbiamo definito an`html` variabile contenente il codice HTML di un selettore con opzioni.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Passaggio 2: imposta le opzioni di caricamento HTML

 Successivamente, creiamo un file`HtmlLoadOptions` oggetto e impostare il`PreferredControlType` proprietà a`HtmlControlType.StructuredDocumentTag`. Questo dice ad Aspose.Words di usare StructuredDocumentTags per rappresentare l'HTML durante il caricamento.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Passaggio 3: caricare e salvare il documento

 Noi usiamo il`Document` class per caricare il codice HTML da un flusso di memoria con le opzioni di caricamento definite in precedenza. Quindi salviamo il documento nella directory specificata con l'estensione`.docx` formato del file.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Codice sorgente di esempio per il tipo di controllo preferito con Aspose.Words per .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

È tutto ! Hai specificato correttamente il tipo di controllo preferito durante il caricamento di un documento HTML con Aspose.Words per .NET.