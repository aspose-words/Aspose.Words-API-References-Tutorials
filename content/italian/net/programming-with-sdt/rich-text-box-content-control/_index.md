---
title: Controllo del contenuto della casella di testo RTF
linktitle: Controllo del contenuto della casella di testo RTF
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come creare un controllo del contenuto di una casella di testo RTF in un documento di Word utilizzando Aspose.Words per .NET abilitando la formattazione e lo stile del testo.
type: docs
weight: 10
url: /it/net/programming-with-sdt/rich-text-box-content-control/
---

Questo tutorial dimostra come creare un controllo del contenuto di una casella di testo RTF in un documento di Word utilizzando Aspose.Words per .NET. I controlli del contenuto ricco delle caselle di testo consentono agli utenti di inserire e formattare il testo con vari stili e opzioni di formattazione.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza base di C# ed elaborazione testi con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui desideri salvare il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: crea un documento e un tag StructuredDocument
 Crea una nuova istanza di`Document` classe e a`StructuredDocumentTag` per rappresentare il controllo del contenuto della casella di testo RTF. Specificare`SdtType.RichText` come il tipo e`MarkupLevel.Block` come livello di markup per creare una casella di testo RTF a livello di blocco.

```csharp
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
```

## Passaggio 3: crea e formatta il contenuto RTF
Crea un paragrafo ed esegui per rappresentare il contenuto RTF. Imposta il testo e le opzioni di formattazione come colore, carattere, ecc.

```csharp
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.Text = "Hello World";
run.Font.Color = Color.Green;
para.Runs.Add(run);
```

## Passaggio 4: aggiungere il contenuto RTF al controllo contenuto
Aggiungi il paragrafo con il contenuto RTF al file`ChildNodes` raccolta del controllo del contenuto della casella di testo RTF.

```csharp
sdtRichText.ChildNodes.Add(para);
```

## Passaggio 5: aggiungi il controllo contenuto al documento
 Aggiungi il controllo del contenuto della casella di testo RTF al corpo del documento utilizzando il comando`AppendChild` metodo del corpo della prima sezione del documento.

```csharp
doc.FirstSection.Body.AppendChild(sdtRichText);
```

## Passaggio 6: salva il documento
 Salvare il documento nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.RichTextBoxContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

### Codice sorgente di esempio per il controllo del contenuto della casella di testo RTF utilizzando Aspose.Words per .NET 

```csharp
	//Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RichText, MarkupLevel.Block);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.Text = "Hello World";
	run.Font.Color = Color.Green;
	para.Runs.Add(run);
	sdtRichText.ChildNodes.Add(para);
	doc.FirstSection.Body.AppendChild(sdtRichText);
	doc.Save(dataDir + "WorkingWithSdt.RichTextBoxContentControl.docx");
```

Questo è tutto! Hai creato con successo un controllo del contenuto della casella di testo RTF nel tuo documento Word utilizzando Aspose.Words per .NET.