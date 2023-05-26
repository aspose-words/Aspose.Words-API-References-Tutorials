---
title: Läs Active XControl-egenskaper
linktitle: Läs Active XControl-egenskaper
second_title: Aspose.Words för .NET API Referens
description: Läs egenskaperna för ActiveX-kontroller i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

I den här steg-för-steg-guiden kommer vi att visa dig hur du läser egenskaperna för ActiveX-kontroller i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

## Steg 1: Dokumentinitiering

 Det första steget är att initiera`Document` objekt genom att ladda Word-dokumentet som innehåller ActiveX-kontrollerna. Se till att byta ut`MyDir` med den faktiska sökvägen till katalogen som innehåller dokumentet.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Steg 2: Återställ ActiveX-kontroller

 I det här steget går vi igenom var och en`Shape` av dokumentet för att hämta ActiveX-kontrollerna och läsa deras egenskaper.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Exempel på källkod för Läs Active XControl Properties med Aspose.Words för .NET

Här är den fullständiga källkoden för att läsa egenskaperna för ActiveX-kontroller med Aspose.Words för .NET:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

