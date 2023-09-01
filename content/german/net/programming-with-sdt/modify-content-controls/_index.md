---
title: Inhaltssteuerelemente ändern
linktitle: Inhaltssteuerelemente ändern
second_title: Aspose.Words-Dokumentverarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Words für .NET Text, Dropdown-Listen und Bilder in Inhaltssteuerelementen in einem Word-Dokument ändern.
type: docs
weight: 10
url: /de/net/programming-with-sdt/modify-content-controls/
---

In diesem Tutorial wird erläutert, wie Sie mit Aspose.Words für .NET verschiedene Arten von Inhaltssteuerelementen in einem Word-Dokument ändern. Sie können den Text oder den ausgewählten Wert einer Dropdown-Liste aktualisieren oder ein Bild innerhalb der Inhaltssteuerelemente ersetzen.

## Voraussetzungen
Um diesem Tutorial folgen zu können, benötigen Sie Folgendes:

- Aspose.Words für .NET-Bibliothek installiert.
- Grundkenntnisse in C# und Textverarbeitung mit Word-Dokumenten.

## Schritt 1: Richten Sie das Dokumentenverzeichnis ein
 Beginnen Sie mit der Einrichtung des Pfads zu Ihrem Dokumentenverzeichnis. Ersetzen`"YOUR DOCUMENT DIRECTORY"` mit dem tatsächlichen Pfad zu dem Verzeichnis, in dem sich Ihr Dokument befindet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Schritt 2: Laden Sie das Dokument und durchlaufen Sie die Inhaltssteuerelemente
 Laden Sie das Word-Dokument mit`Document`Konstruktor, der den Pfad zum Dokument als Parameter übergibt. Durchlaufen Sie alle strukturierten Dokument-Tags im Dokument mit a`foreach` Schleife.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Führen Sie Aktionen basierend auf der Art der Inhaltskontrolle aus
}
```

## Schritt 3: Ändern Sie die Inhaltssteuerung für Nur-Text
 Für Inhaltssteuerelemente vom Typ`SdtType.PlainText`, entfernen Sie alle vorhandenen untergeordneten Elemente, erstellen Sie einen neuen Absatz und hängen Sie eine Zeile mit dem gewünschten Text an.

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

## Schritt 4: Ändern Sie die Inhaltssteuerung der Dropdown-Liste
 Für Inhaltssteuerelemente vom Typ`SdtType.DropDownList` , aktualisieren Sie den ausgewählten Wert, indem Sie ihn auf einen bestimmten Wert festlegen`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Schritt 5: Ändern Sie die Bildinhaltssteuerung
 Für Inhaltssteuerelemente vom Typ`SdtType.Picture`, rufen Sie die Form im Inhaltssteuerelement ab und ersetzen Sie das Bild durch ein neues.

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
 Speichern Sie das geänderte Dokument mit im angegebenen Verzeichnis`Save` Methode. Geben Sie den gewünschten Dateinamen mit der entsprechenden Dateierweiterung an. In diesem Beispiel speichern wir das Dokument als „WorkingWithSdt.ModifyContentControls.docx“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Beispielquellcode für die Änderung von Inhaltssteuerelementen mit Aspose.Words für .NET 

```csharp
	// Pfad zu Ihrem Dokumentenverzeichnis
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

Das ist es! Sie haben mit Aspose.Words für .NET erfolgreich verschiedene Arten von Inhaltssteuerelementen in Ihrem Word-Dokument geändert.