---
title: Modifica i controlli del contenuto
linktitle: Modifica i controlli del contenuto
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come modificare testo, elenchi a discesa e immagini all'interno dei controlli del contenuto in un documento di Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/modify-content-controls/
---

Questo tutorial spiega come modificare diversi tipi di controlli del contenuto in un documento di Word utilizzando Aspose.Words per .NET. È possibile aggiornare il testo, il valore selezionato di un elenco a discesa o sostituire un'immagine all'interno dei controlli del contenuto.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza di base di C# e lavoro con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento e iterare sui controlli del contenuto
 Carica il documento Word usando il file`Document`costruttore, passando il percorso al documento come parametro. Iterare su tutti i tag del documento strutturato nel documento utilizzando a`foreach` ciclo continuo.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Eseguire azioni in base al tipo di controllo del contenuto
}
```

## Passaggio 3: modifica del controllo del contenuto in testo normale
 Per i controlli del contenuto di tipo`SdtType.PlainText`, rimuovi tutti i figli esistenti, crea un nuovo paragrafo e aggiungi una sequenza con il testo desiderato.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## Passaggio 4: modificare il controllo del contenuto dell'elenco a discesa
 Per i controlli del contenuto di tipo`SdtType.DropDownList` , aggiornare il valore selezionato impostandolo su un valore specifico`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Passaggio 5: modificare il controllo del contenuto dell'immagine
 Per i controlli del contenuto di tipo`SdtType.Picture`, recuperare la forma all'interno del controllo contenuto e sostituirne l'immagine con una nuova.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## Passaggio 6: salvare il documento modificato
 Salvare il documento modificato nella directory specificata utilizzando il file`Save` metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.ModifyContentControls.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Codice sorgente di esempio per modificare i controlli del contenuto utilizzando Aspose.Words per .NET 

```csharp
	// Percorso della directory dei documenti
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

Questo è tutto! Hai modificato correttamente diversi tipi di controlli del contenuto nel documento di Word utilizzando Aspose.Words per .NET.