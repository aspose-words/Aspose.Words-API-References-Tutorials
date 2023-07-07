---
title: Läs Active XControl-egenskaper från Word-fil
linktitle: Läs Active XControl-egenskaper från Word-fil
second_title: Aspose.Words för .NET API Referens
description: Läs egenskaperna för ActiveX-kontroller i en Word-fil med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

I den här steg-för-steg-guiden kommer vi att visa dig hur du läser egenskaperna för ActiveX-kontroller i en Word-fil med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

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

## Slutsats

Den här guiden visade hur du läser egenskaperna för ActiveX-kontroller i en Word-fil med Aspose.Words för .NET. Genom att följa de beskrivna stegen kan du initiera dokumentet, hämta ActiveX-kontroller och läsa deras egenskaper. Använd exempelkoden som tillhandahålls som utgångspunkt och anpassa den efter dina specifika behov.

Genom att läsa egenskaperna för ActiveX-kontroller kan du extrahera viktig information från dina Word-filer som innehåller dessa kontroller. Aspose.Words för .NET erbjuder kraftfulla funktioner för att arbeta med ActiveX-kontroller och automatisera din dokumentbehandling.

### Vanliga frågor

#### F: Vad är det första steget för att läsa egenskaperna för ActiveX-kontroller i en Word-fil?

 S: Det första steget är att initiera`Document` objekt genom att ladda Word-dokumentet som innehåller ActiveX-kontrollerna. Se till att byta ut`MyDir` med den faktiska sökvägen till katalogen som innehåller dokumentet.

#### F: Hur får jag in ActiveX-kontroller i dokumentet?

 S: För att hämta ActiveX-kontroller måste du iterera igenom var och en`Shape` av dokumentet och kontrollera om det är en ActiveX-kontroll. Använd`OleFormat` egendom av`Shape` för att komma åt`OleControl` objekt och hämta de nödvändiga egenskaperna.

#### F: Vilka egenskaper för ActiveX-kontroller kan jag läsa?

S: Du kan läsa olika egenskaper för ActiveX-kontroller, såsom bildtext, värde, aktiverat eller inaktiverat tillstånd, typ och barnnoder som är associerade med kontrollen.

#### F: Hur kan jag få det totala antalet ActiveX-kontroller i dokumentet?

 S: För att få det totala antalet ActiveX-kontroller i dokumentet kan du använda`GetChildNodes` metod för`Document` objekt som anger`NodeType.Shape` typ och inklusive underordnade noder.