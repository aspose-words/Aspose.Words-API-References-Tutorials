---
title: Ändra innehållskontroller
linktitle: Ändra innehållskontroller
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ändrar text, rullgardinslistor och bilder i innehållskontroller i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/modify-content-controls/
---

Denna handledning förklarar hur du ändrar olika typer av innehållskontroller i ett Word-dokument med Aspose.Words för .NET. Du kan uppdatera texten, det valda värdet i en rullgardinslista eller ersätta en bild i innehållskontrollerna.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda dokumentet och upprepa innehållskontrollerna
 Ladda Word-dokumentet med hjälp av`Document` konstruktor, skickar sökvägen till dokumentet som en parameter. Iterera över alla strukturerade dokumenttaggar i dokumentet med hjälp av en`foreach` slinga.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Utför åtgärder baserat på typen av innehållskontroll
}
```

## Steg 3: Ändra innehållskontroll för vanlig text
 För innehållskontroller av typ`SdtType.PlainText`, ta bort alla befintliga underordnade, skapa ett nytt stycke och lägg till en körning med önskad text.

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

## Steg 4: Ändra innehållskontroll i rullgardinsmenyn
 För innehållskontroller av typ`SdtType.DropDownList` , uppdatera det valda värdet genom att ställa in det till ett specifikt`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Steg 5: Ändra bildinnehållskontroll
 För innehållskontroller av typ`SdtType.Picture`, hämta formen i innehållskontrollen och ersätt dess bild med en ny.

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

## Steg 6: Spara det ändrade dokumentet
 Spara det ändrade dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithSdt.ModifyContentControls.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Exempel på källkod för Ändra innehållskontroller med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
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

Det är allt! Du har framgångsrikt modifierat olika typer av innehållskontroller i ditt Word-dokument med Aspose.Words för .NET.