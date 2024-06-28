---
title: Word lid van een nieuwe pagina
linktitle: Word lid van een nieuwe pagina
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u twee documenten op een nieuwe pagina kunt samenvoegen met behoud van de opmaak met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/join-new-page/
---

In deze zelfstudie wordt uitgelegd hoe u twee documenten op een nieuwe pagina kunt samenvoegen met Aspose.Words voor .NET. De meegeleverde broncode laat zien hoe u een document aan het einde van een ander document kunt toevoegen terwijl u het toegevoegde document op een nieuwe pagina begint.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

-  Aspose.Words voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van[Aspose.Releases]https://releases.aspose.com/words/net/ of gebruik NuGet-pakketbeheer om het te installeren.
- Een documentmappad waar de bron- en doeldocumenten zich bevinden.

## Stap 2: Open de bron- en doeldocumenten

 Open de bron- en doeldocumenten met behulp van de`Document` klasse constructor. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Stap 3: Stel het begin van een nieuwe paginasectie in

 Om het toegevoegde document op een nieuwe pagina te laten beginnen, stelt u de`SectionStart` eigenschap van de eerste sectie in het brondocument`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Stap 4: Voeg het brondocument toe

 Voeg het brondocument toe aan het doeldocument met behulp van de`AppendDocument` werkwijze van de`Document` klas. Stel de importformaatmodus in op`ImportFormatMode.KeepSourceFormatting` om de originele stijlen uit het brondocument te behouden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 5: Sla het gewijzigde document op

Sla ten slotte het gewijzigde bestemmingsdocument op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

Hiermee is de implementatie voltooid van het samenvoegen van twee documenten op een nieuwe pagina met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor Join New Page met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Stel in dat het toegevoegde document op een nieuwe pagina begint.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Voeg het brondocument toe met behulp van de originele stijlen uit het brondocument.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```