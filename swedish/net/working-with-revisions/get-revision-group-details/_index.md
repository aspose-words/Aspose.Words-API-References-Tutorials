---
title: Få information om revisionsgruppen
linktitle: Få information om revisionsgruppen
second_title: Aspose.Words för .NET API Referens
description: Få detaljer om revisionsgrupp i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/get-revision-group-details/
---

I den här steg-för-steg-guiden kommer vi att visa dig hur du får information om en grupp revisioner i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

## Steg 1: Ladda dokumentet

Det första steget är att ladda upp dokumentet som innehåller ändringarna.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## Steg 2: Bläddra i versioner

Därefter går vi igenom de versioner som finns i dokumentet och visar deras detaljer, såsom typ, författare, datum och reviderad text.

```csharp
foreach (Revision revision in doc.Revisions)
{
     string groupText = revision.Group != null
         ? "Revision group text: " + revision.Group.Text
         : "The revision does not belong to any group";

     Console.WriteLine("Type: " + revision.RevisionType);
     Console.WriteLine("Author: " + revision.Author);
     Console.WriteLine("Date: " + revision.DateTime);
     Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
     Console.WriteLine(groupText);
}
```


### Exempel på källkod för Get Revision Group Details med Aspose.Words för .NET

Här är den fullständiga källkoden för att få information om en grupp revisioner i ett dokument med Aspose.Words för .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

foreach (Revision revision in doc.Revisions)
{
	 string groupText = revision.Group != null
		 ? "Revision group text: " + revision.Group.Text
		 : "The revision does not belong to any group";

	 Console.WriteLine("Type: " + revision.RevisionType);
	 Console.WriteLine("Author: " + revision.Author);
	 Console.WriteLine("Date: " + revision.DateTime);
	 Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
	 Console.WriteLine(groupText);
}
```

## Slutsats

den här självstudien lärde vi oss hur man får information om en grupp revisioner i ett Word-dokument med Aspose.Words för .NET. Genom att använda en loop och lämpliga egenskaper kunde vi visa detaljer som revisionstyp, författare, datum och reviderad text. Aspose.Words för .NET erbjuder många kraftfulla funktioner för att manipulera Word-dokument, inklusive revisionshantering. Du kan nu använda den här kunskapen för att få detaljer om revisionsgrupp till dina egna Word-dokument med Aspose.Words för .NET.

### FAQ's

#### F: Hur laddar jag ett dokument med ändringar i Aspose.Words för .NET?

 A: Använd`Document`klass av Aspose.Words för .NET för att ladda ett dokument från en fil som innehåller revisioner. Du kan ange hela dokumentsökvägen.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Hur får jag information om en revisionsgrupp i Aspose.Words för .NET?

 S: Gå igenom versionerna av dokumentet med hjälp av en loop och få tillgång till egenskaperna för varje version för att få de detaljer du vill ha. Du kan använda`RevisionType`, `Author`, `DateTime` och`ParentNode` egenskaper för att få revisionstyp, författare, datum respektive reviderad text.

```csharp
foreach (Revision revision in doc.Revisions)
{
      Console.WriteLine("Type: " + revision.RevisionType

);
      Console.WriteLine("Author: " + revision.Author);
      Console.WriteLine("Date: " + revision.DateTime);
      Console.WriteLine("Revision text: " + revision.ParentNode.ToString(SaveFormat.Text));
}
```

#### F: Hur kontrollerar man om en revision tillhör en grupp i Aspose.Words för .NET?

 A: Använd`Group` egendom av`Revision` objekt för att kontrollera om en revision tillhör en grupp. Om`Group` egendom är`null`betyder det att revisionen inte tillhör någon grupp.

```csharp
if (revision.Group != null)
{
      // Revisionen tillhör en grupp
}
else
{
      // Revisionen tillhör inte någon grupp
}
```