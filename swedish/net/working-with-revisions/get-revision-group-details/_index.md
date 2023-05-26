---
title: Få information om revisionsgruppen
linktitle: Få information om revisionsgruppen
second_title: Aspose.Words för .NET API Referens
description: Få detaljer om revisionsgrupp i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/get-revision-group-details/
---

den här steg-för-steg-guiden kommer vi att visa dig hur du får information om en grupp revisioner i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

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

