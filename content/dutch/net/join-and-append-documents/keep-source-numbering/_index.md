---
title: Behoud de bronnummering
linktitle: Behoud de bronnummering
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u documenten importeert met behoud van de opmaak met Aspose.Words voor .NET. Stapsgewijze handleiding met codevoorbeelden.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/keep-source-numbering/
---
## Invoering

 Wanneer u met Aspose.Words voor .NET werkt, kan het importeren van documenten van de ene bron naar de andere met behoud van de opmaak efficiënt worden afgehandeld met behulp van de`NodeImporter` klas. Deze tutorial begeleidt u stap voor stap door het proces.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:
- Visual Studio is op uw computer geïnstalleerd.
-  Aspose.Words voor .NET geïnstalleerd. Zo niet, download het dan van[hier](https://releases.aspose.com/words/net/).
- Basiskennis van programmeren in C# en .NET.

## Naamruimten importeren

Neem eerst de benodigde naamruimten op in uw project:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## Stap 1: Stel uw project in

Begin met het maken van een nieuw C#-project in Visual Studio en installeer Aspose.Words via NuGet Package Manager.

## Stap 2: Initialiseer documenten
Maak exemplaren van de bron (`srcDoc`) en bestemming (`dstDoc`) documenten.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Stap 3: Configureer importopties
Stel importopties in om de bronopmaak te behouden, inclusief genummerde alinea's.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## Stap 4: importeer alinea's
Blader door de alinea's in het brondocument en importeer ze in het doeldocument.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Stap 5: Bewaar het document
Sla het samengevoegde document op de gewenste locatie op.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## Conclusie

 Concluderend: het gebruik van Aspose.Words voor .NET om documenten te importeren met behoud van de opmaak is eenvoudig met de`NodeImporter` klas. Deze methode zorgt ervoor dat uw documenten naadloos hun oorspronkelijke uiterlijk en structuur behouden.

## Veelgestelde vragen

### Kan ik documenten met verschillende opmaakstijlen importeren?
 Ja de`NodeImporter` class ondersteunt het importeren van documenten met verschillende opmaakstijlen.

### Wat moet ik doen als mijn documenten complexe tabellen en afbeeldingen bevatten?
Aspose.Words voor .NET verwerkt complexe structuren zoals tabellen en afbeeldingen tijdens importbewerkingen.

### Is Aspose.Words compatibel met alle versies van .NET?
Aspose.Words ondersteunt .NET Framework- en .NET Core-versies voor naadloze integratie.

### Hoe kan ik omgaan met fouten tijdens het importeren van documenten?
Gebruik try-catch-blokken om uitzonderingen af te handelen die kunnen optreden tijdens het importproces.

### Waar kan ik meer gedetailleerde documentatie vinden over Aspose.Words voor .NET?
 Bezoek de[documentatie](https://reference.aspose.com/words/net/) voor uitgebreide handleidingen en API-referenties.
