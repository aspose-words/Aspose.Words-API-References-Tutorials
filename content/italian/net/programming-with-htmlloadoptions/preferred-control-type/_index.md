---
title: Tipo di controllo preferito nel documento Word
linktitle: Tipo di controllo preferito nel documento Word
second_title: API di elaborazione dei documenti Aspose.Words
description: Guida passo passo per specificare il tipo di controllo preferito nel documento Word quando si carica un documento HTML con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-htmlloadoptions/preferred-control-type/
---
Questo articolo fornisce una guida passo passo su come utilizzare la funzionalità del tipo di controllo preferito con Aspose.Words per .NET. Spiegheremo ogni parte del codice in dettaglio. Alla fine di questo tutorial sarai in grado di capire come specificare il tipo di controllo preferito durante il caricamento di un documento HTML.

Prima di iniziare, assicurati di aver installato e configurato la libreria Aspose.Words per .NET nel tuo progetto. È possibile trovare la libreria e le istruzioni di installazione sul sito Web Aspose.

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

 Successivamente, creiamo un file`HtmlLoadOptions` oggetto e impostare il`PreferredControlType`proprietà a`HtmlControlType.StructuredDocumentTag`. Questo indica ad Aspose.Words di utilizzare StructuredDocumentTags per rappresentare HTML durante il caricamento.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Passaggio 3: caricare e salvare il documento

 Noi usiamo il`Document` classe per caricare il codice HTML da un flusso di memoria con le opzioni di caricamento definite in precedenza. Quindi salviamo il documento nella directory specificata con il file`.docx`formato del file.

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

È tutto ! Hai specificato con successo il tipo di controllo preferito durante il caricamento di un documento HTML con Aspose.Words per .NET.

## Conclusione

 Seguendo questa guida passo passo, hai imparato come utilizzare la funzione "Tipo di controllo preferito" in Aspose.Words per .NET per specificare il tipo di controllo desiderato durante il caricamento di un documento HTML. Impostazione del`PreferredControlType`proprietà a`HtmlControlType.StructuredDocumentTag` consente ad Aspose.Words di utilizzare StructuredDocumentTags (SDT) per una migliore rappresentazione ed elaborazione del contenuto HTML. Puoi esplorare anche altri tipi di controllo per soddisfare le tue esigenze specifiche. L'utilizzo di questa funzionalità aiuta a garantire una gestione accurata ed efficiente dei documenti HTML nell'applicazione C# con Aspose.Words.

### Domande frequenti sul tipo di controllo preferito nel documento Word

#### D: Qual è la funzionalità "Tipo di controllo preferito" in Aspose.Words per .NET?

R: La funzione "Tipo di controllo preferito" ti consente di specificare il tipo di controllo preferito per rappresentare gli elementi HTML durante il caricamento di un documento HTML. Aiuta a selezionare il tipo di controllo appropriato per una migliore rappresentazione ed elaborazione del contenuto HTML.

#### D: Come posso impostare il tipo di controllo preferito durante il caricamento di un documento HTML?

 R: Per impostare il tipo di controllo preferito, è necessario creare un file`HtmlLoadOptions` oggetto e impostarlo`PreferredControlType` proprietà a quella desiderata`HtmlControlType` . Nell'esempio fornito,`HtmlControlType.StructuredDocumentTag` si usa.

#### D: Qual è il significato dell'utilizzo di StructuredDocumentTags (SDT) come tipo di controllo preferito?

R: StructuredDocumentTag (SDT) sono elementi basati su XML che possono essere utilizzati per rappresentare contenuti e controlli complessi in un documento di Word. L'utilizzo degli SDT come tipo di controllo preferito può fornire una migliore compatibilità e rappresentazione del contenuto HTML.

#### D: Come posso assicurarmi che Aspose.Words utilizzi il tipo di controllo preferito durante il caricamento del documento HTML?

 R: Impostando il`PreferredControlType`proprietà a`HtmlControlType.StructuredDocumentTag`come mostrato nel codice sorgente di esempio, Aspose.Words utilizzerà gli SDT per rappresentare gli elementi HTML durante il caricamento del documento.

#### D: Posso utilizzare altri tipi di controllo come opzione preferita?

 R: Sì, a parte`HtmlControlType.StructuredDocumentTag` , Aspose.Words per .NET supporta altri tipi di controllo come`HtmlControlType.ContentControl` E`HtmlControlType.CustomXmlMarkup`.