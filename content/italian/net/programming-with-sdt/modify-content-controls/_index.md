---
title: Modifica i controlli del contenuto
linktitle: Modifica i controlli del contenuto
second_title: API di elaborazione dei documenti Aspose.Words
description: Scopri come modificare testo, elenchi a discesa e immagini all'interno dei controlli contenuto in un documento Word utilizzando Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-sdt/modify-content-controls/
---

Questo tutorial spiega come modificare diversi tipi di controlli del contenuto in un documento di Word utilizzando Aspose.Words per .NET. Puoi aggiornare il testo, il valore selezionato di un elenco a discesa o sostituire un'immagine all'interno dei controlli del contenuto.

## Prerequisiti
Per seguire questo tutorial, è necessario disporre di quanto segue:

- Aspose.Words per la libreria .NET installata.
- Conoscenza base di C# ed elaborazione testi con documenti Word.

## Passaggio 1: impostare la directory dei documenti
 Inizia impostando il percorso della directory dei documenti. Sostituire`"YOUR DOCUMENT DIRECTORY"` con il percorso effettivo della directory in cui si trova il documento.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Passaggio 2: caricare il documento e ripetere i controlli del contenuto
 Caricare il documento Word utilizzando il file`Document` costruttore, passando il percorso del documento come parametro. Itera su tutti i tag del documento strutturato nel documento utilizzando a`foreach` ciclo continuo.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Esegui azioni in base al tipo di controllo del contenuto
}
```

## Passaggio 3: modificare il controllo del contenuto in testo semplice
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
 Per i controlli del contenuto di tipo`SdtType.DropDownList` , aggiorna il valore selezionato impostandolo su uno specifico`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Passaggio 5: modificare il controllo del contenuto dell'immagine
 Per i controlli del contenuto di tipo`SdtType.Picture`, recupera la forma all'interno del controllo contenuto e sostituisci la relativa immagine con una nuova.

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

## Passaggio 6: salva il documento modificato
 Salvare il documento modificato nella directory specificata utilizzando il file`Save`metodo. Fornire il nome file desiderato con l'estensione file appropriata. In questo esempio, salviamo il documento come "WorkingWithSdt.ModifyContentControls.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Codice sorgente di esempio per Modifica controlli contenuto utilizzando Aspose.Words per .NET 

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

Questo è tutto! Hai modificato con successo diversi tipi di controlli del contenuto nel tuo documento Word utilizzando Aspose.Words per .NET.