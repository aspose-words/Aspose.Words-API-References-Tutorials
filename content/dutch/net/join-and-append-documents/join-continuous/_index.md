---
title: Sluit je aan bij Continu
linktitle: Sluit je aan bij Continu
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u twee documenten continu kunt samenvoegen met behoud van de opmaak met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/join-continuous/
---

In deze zelfstudie wordt uitgelegd hoe u twee documenten continu kunt samenvoegen met Aspose.Words voor .NET. De meegeleverde broncode laat zien hoe u een document aan het einde van een ander document kunt toevoegen met behoud van de oorspronkelijke opmaak.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

-  Aspose.Words voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van[Aspose.Releases]https://releases.aspose.com/words/net/ of gebruik NuGet-pakketbeheer om het te installeren.
- Een documentmappad waar de bron- en doeldocumenten zich bevinden.

## Stap 2: Open de bron- en doeldocumenten

 Open de bron- en doeldocumenten met behulp van de`Document` klasse constructeur. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Stap 3: Doorlopende sectiestart instellen

 Om het brondocument direct na de inhoud van het doeldocument te laten verschijnen, stelt u de`SectionStart` eigenschap van de eerste sectie in het brondocument`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Stap 4: Voeg het brondocument toe

 Voeg het brondocument toe aan het doeldocument met behulp van de`AppendDocument` werkwijze van de`Document` klas. Stel de importformaatmodus in op`ImportFormatMode.KeepSourceFormatting` om de originele stijlen uit het brondocument te behouden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 5: Sla het gewijzigde document op

 Sla ten slotte het gewijzigde bestemmingsdocument op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

Hiermee is de implementatie voltooid van het continu samenvoegen van twee documenten met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor Join Continuous met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Zorg ervoor dat het document direct na de inhoud van het doeldocument verschijnt.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Voeg het brondocument toe met behulp van de originele stijlen uit het brondocument.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```