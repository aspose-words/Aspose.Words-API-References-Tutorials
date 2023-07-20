---
title: Få tillgång till reviderad version
linktitle: Få tillgång till reviderad version
second_title: Aspose.Words Document Processing API
description: Få tillgång till en reviderad version av ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/access-revised-version/
---

I den här steg-för-steg-guiden kommer vi att visa dig hur du kommer åt den reviderade versionen av ett Word-dokument med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

## Steg 1: Ladda dokumentet

Det första steget är att ladda upp dokumentet som innehåller ändringarna.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Steg 2: Få tillgång till den reviderade versionen

Vi går nu vidare till den reviderade versionen av dokumentet.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Steg 3: Bläddra i versioner

Därefter går vi igenom de versioner som finns i dokumentet och visar specifik information för stycken som är listobjekt.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Exempel på källkod för Access Revised Version med Aspose.Words för .NET

Här är den fullständiga källkoden för att komma åt den reviderade versionen av ett dokument med Aspose.Words för .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Byt till den reviderade versionen av dokumentet.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## Slutsats

I den här handledningen lärde vi oss hur man kommer åt den reviderade versionen av ett Word-dokument med Aspose.Words för .NET. Genom att ladda dokumentet, navigera till den reviderade versionen och bläddra igenom revisionerna kunde vi få specifik information för stycken som är listobjekt. Aspose.Words för .NET erbjuder kraftfulla funktioner för att manipulera Word-dokument, inklusive tillgång till recensioner. Du kan nu använda denna kunskap för att komma åt den reviderade versionen av dina egna Word-dokument med Aspose.Words för .NET.

### FAQ's

#### F: Hur laddar jag ett dokument med ändringar i Aspose.Words för .NET?

 A: Använd`Document`klass av Aspose.Words för .NET för att ladda ett dokument från en fil som innehåller revisioner. Du kan ange hela dokumentsökvägen.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Hur kommer jag åt den reviderade versionen av ett dokument i Aspose.Words för .NET?

 A: Använd`RevisionsView` egendom av`Document` objekt för att komma åt den reviderade versionen av dokumentet. Du kan ställa in värdet på`RevisionsView` egendom till`RevisionsView.Final` för att visa den slutliga versionen utan ändringarna.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### F: Hur bläddrar jag i dokumentrevisioner i Aspose.Words för .NET?

 A: Använd a`foreach` loop för att iterera genom de versioner som finns i dokumentet. Du kan använda`Revisions` egendom av`Document` objekt för att få en samling av alla versioner av dokumentet.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Bearbeta varje revision här
}
```

#### F: Hur kontrollerar man om ett stycke är ett listobjekt i Aspose.Words för .NET?

 A: Använd`IsListItem` egendom av`Paragraph` objekt för att kontrollera om ett stycke är ett listobjekt. De`IsListItem` egendom returnerar`true` om stycket är ett listobjekt, annars returneras det`false`.

```csharp
if (paragraph.IsListItem)
{
     // Stycket är ett listobjekt
}
else
{
     // Stycket är inte ett listobjekt
}
```