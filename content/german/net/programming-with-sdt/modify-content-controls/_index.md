---
title: Inhaltssteuerelemente ändern
linktitle: Inhaltssteuerelemente ändern
second_title: Aspose.Words Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Text, Dropdown-Listen und Bilder in Inhaltssteuerelementen in einem Word-Dokument ändern.
type: docs
weight: 10
url: /de/net/programming-with-sdt/modify-content-controls/
---

In diesem Tutorial wird erklärt, wie Sie mit Aspose.Words für .NET verschiedene Arten von Inhaltssteuerelementen in einem Word-Dokument ändern. Sie können den Text, den ausgewählten Wert einer Dropdown-Liste aktualisieren oder ein Bild innerhalb der Inhaltssteuerelemente ersetzen.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Einrichten des Dokumentverzeichnisses
 Beginnen Sie mit der Einrichtung des Pfades zu Ihrem Dokumentverzeichnis. Ersetzen Sie`"YOUR DOCUMENT DIRECTORY"` durch den tatsächlichen Pfad zum Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und durchlaufen Sie die Inhaltssteuerelemente
 Laden Sie das Word-Dokument mit dem`Document` Konstruktor, wobei der Pfad zum Dokument als Parameter übergeben wird. Iterieren Sie über alle strukturierten Dokument-Tags im Dokument mit einem`foreach` Schleife.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Ausführen von Aktionen basierend auf der Art der Inhaltskontrolle
}
```

## Schritt 3: Ändern des Nur-Text-Inhaltssteuerelements
 Für Inhaltssteuerelemente vom Typ`SdtType.PlainText`, entfernen Sie alle vorhandenen untergeordneten Elemente, erstellen Sie einen neuen Absatz und fügen Sie einen Lauf mit dem gewünschten Text an.

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

## Schritt 4: Dropdown-Listen-Inhaltssteuerelement ändern
 Für Inhaltssteuerelemente vom Typ`SdtType.DropDownList` , aktualisieren Sie den ausgewählten Wert, indem Sie ihn auf einen bestimmten`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Schritt 5: Bildinhaltssteuerung ändern
 Für Inhaltssteuerelemente vom Typ`SdtType.Picture`, rufen Sie die Form innerhalb des Inhaltssteuerelements ab und ersetzen Sie das Bild durch ein neues.

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

## Schritt 6: Speichern Sie das geänderte Dokument
 Speichern Sie das geänderte Dokument im angegebenen Verzeichnis mit dem`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.ModifyContentControls.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Beispielquellcode zum Ändern von Inhaltssteuerelementen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentverzeichnis
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

Das ist es! Sie haben erfolgreich verschiedene Arten von Inhaltssteuerelementen in Ihrem Word-Dokument mit Aspose.Words für .NET geändert.