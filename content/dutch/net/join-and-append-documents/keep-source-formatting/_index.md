---
title: Behoud de bronopmaak
linktitle: Behoud de bronopmaak
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een brondocument aan een doeldocument kunt toevoegen met behoud van de oorspronkelijke opmaak met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/keep-source-formatting/
---

In deze zelfstudie wordt gedemonstreerd hoe u een brondocument aan een doeldocument kunt toevoegen terwijl de oorspronkelijke opmaak van het brondocument behouden blijft met behulp van Aspose.Words voor .NET.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

-  Aspose.Words voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van[Aspose.Releases]https://releases.aspose.com/words/net/ of gebruik NuGet-pakketbeheer om het te installeren.
- Een documentmappad waar de bron- en doeldocumenten worden opgeslagen.

## Stap 2: Maak de bestemmings- en brondocumenten

 Maak exemplaren van`Document` voor de bestemmings- en brondocumenten.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Stap 3: Voeg het brondocument toe aan het doeldocument

 Gebruik de`AppendDocument` methode van het doeldocument om het brondocument toe te voegen. Doorgang`ImportFormatMode.KeepSourceFormatting` als importformaatmodus om de originele opmaak van het brondocument te behouden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 4: Sla het gewijzigde document op

 Sla het gewijzigde document op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Hiermee is de implementatie voltooid van het toevoegen van een brondocument aan een doeldocument terwijl de oorspronkelijke opmaak behouden blijft met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor Bronopmaak behouden met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Voeg het brondocument toe aan het doeldocument.
	// Geef de formatteringsmodus door om de oorspronkelijke opmaak van het brondocument te behouden bij het importeren ervan.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```