---
title: Houd de bron bij elkaar
linktitle: Houd de bron bij elkaar
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Aspose.Words voor .NET kunt gebruiken om Word-documenten samen te voegen en toe te voegen, terwijl de broninhoud bij het doeldocument blijft.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/keep-source-together/
---

Deze tutorial begeleidt u bij het gebruik van de functie Keep Source Together van Aspose.Words voor .NET. Met deze functie kunt u meerdere Word-documenten samenvoegen en toevoegen, terwijl de inhoud van het brondocument samen blijft met de inhoud van het doeldocument. 

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

1. Aspose.Words voor .NET geïnstalleerd. Je kunt het downloaden van de Aspose-website of installeren via NuGet.
2. Visual Studio of een andere C#-ontwikkelomgeving.

## Stap 1: Initialiseer de documentmappen

 Eerst moet u het pad naar uw documentmap instellen. Wijzig de waarde van de`dataDir` variabele naar het pad waar uw documenten zich bevinden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad de bron- en doeldocumenten

Vervolgens moet u de bron- en doeldocumenten laden met behulp van Aspose.Words`Document` klas. Werk de bestandsnamen bij in het`Document` constructor volgens uw documentnamen.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Stap 3: Stel in dat het brondocument na de inhoud van het doeldocument verschijnt

 Om ervoor te zorgen dat het brondocument onmiddellijk na de inhoud van het doeldocument verschijnt, moet u de`SectionStart` eigenschap van de eerste sectie in het brondocument`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Stap 4: Stel de alineaopmaak "Bewaar bij volgende" in voor het brondocument

 Om de alinea's in het brondocument bij elkaar te houden, kunt u elke alinea in het document doorlopen en de`KeepWithNext`eigendom aan`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Stap 5: Voeg het brondocument toe aan het doeldocument

 Nu kunt u het brondocument aan het doeldocument toevoegen met behulp van de`AppendDocument` werkwijze van de`Document` klas. De`ImportFormatMode.KeepSourceFormatting` parameter zorgt ervoor dat de bronopmaak behouden blijft tijdens de toevoegbewerking.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 6: Bewaar het definitieve document

 Sla ten slotte het samengevoegde document op met de functie "Keep Source Together" ingeschakeld met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Voorbeeldbroncode voor Keep Source Together met Aspose.Words voor .NET 

Hier is de volledige broncode voor de functie "Keep Source Together" in C# met behulp van Aspose.Words voor .NET:


```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Stel in dat het brondocument direct na de inhoud van het doeldocument verschijnt.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Dat is het! U hebt de functie Keep Source Together met succes geïmplementeerd met Aspose.Words voor .NET. Het uiteindelijke document bevat de samengevoegde inhoud, waarbij de paragrafen in het brondocument bij elkaar worden gehouden.