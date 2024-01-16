---
title: Lees Active XControl-eigenschappen uit een Word-bestand
linktitle: Lees Active XControl-eigenschappen uit een Word-bestand
second_title: Aspose.Words-API voor documentverwerking
description: Lees eigenschappen van ActiveX-besturingselementen in een Word-bestand met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

In deze stapsgewijze handleiding laten we u zien hoe u de eigenschappen van ActiveX-besturingselementen in een Word-bestand kunt lezen met behulp van Aspose.Words voor .NET. We voorzien u van de volledige broncode en laten u zien hoe u de markdown-uitvoer kunt formatteren.

## Stap 1: Documentinitialisatie

 De eerste stap is het initialiseren van de`Document` object door het Word-document met de ActiveX-besturingselementen te laden. Zeker vervangen`MyDir` met het daadwerkelijke pad naar de map die het document bevat.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## Stap 2: Herstel ActiveX-besturingselementen

 In deze stap zullen we ze allemaal doorlopen`Shape` van het document om de ActiveX-besturingselementen op te halen en hun eigenschappen te lezen.

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

### Voorbeeldbroncode voor Read Active XControl Properties met Aspose.Words voor .NET

Hier is de volledige broncode voor het lezen van eigenschappen van ActiveX-besturingselementen met Aspose.Words voor .NET:

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

## Conclusie

In deze handleiding werd uitgelegd hoe u de eigenschappen van ActiveX-besturingselementen in een Word-bestand kunt lezen met Aspose.Words voor .NET. Door de beschreven stappen te volgen, kunt u het document initialiseren, ActiveX-besturingselementen ophalen en hun eigenschappen lezen. Gebruik de meegeleverde voorbeeldcode als uitgangspunt en pas deze aan uw specifieke behoeften aan.

Door de eigenschappen van ActiveX-besturingselementen te lezen, kunt u belangrijke informatie extraheren uit uw Word-bestanden die deze besturingselementen bevatten. Aspose.Words voor .NET biedt krachtige functies voor woordenverwerking met ActiveX-besturingselementen en het automatiseren van uw documentverwerking.

### Veelgestelde vragen

#### Vraag: Wat is de eerste stap om de eigenschappen van ActiveX-besturingselementen in een Word-bestand te lezen?

 A: De eerste stap is het initialiseren van het`Document` object door het Word-document met de ActiveX-besturingselementen te laden. Zeker vervangen`MyDir` met het daadwerkelijke pad naar de map die het document bevat.

#### Vraag: Hoe krijg ik ActiveX-besturingselementen in het document?

 A: Om ActiveX-besturingselementen op te halen, moet u ze allemaal doorlopen`Shape` van het document en controleer of het een ActiveX-besturingselement is. Gebruik de`OleFormat` eigendom van`Shape` om toegang te krijgen tot de`OleControl` object en haal de benodigde eigenschappen op.

#### Vraag: Welke eigenschappen van ActiveX-besturingselementen kan ik lezen?

A: U kunt verschillende eigenschappen van ActiveX-besturingselementen lezen, zoals bijschrift, waarde, ingeschakelde of uitgeschakelde status, type en onderliggende knooppunten die aan het besturingselement zijn gekoppeld.

#### Vraag: Hoe kan ik het totale aantal ActiveX-besturingselementen in het document verkrijgen?

 A: Om het totale aantal ActiveX-besturingselementen in het document te achterhalen, kunt u de`GetChildNodes` werkwijze van de`Document` object dat de specificatie specificeert`NodeType.Shape` type en inclusief de onderliggende knooppunten.