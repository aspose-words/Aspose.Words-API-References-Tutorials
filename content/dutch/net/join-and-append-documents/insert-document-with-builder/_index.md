---
title: Document invoegen met Builder
linktitle: Document invoegen met Builder
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een document aan het einde van een ander document kunt invoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/insert-document-with-builder/
---

 In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET gebruikt om een document in een ander document in te voegen met behulp van de`DocumentBuilder` klas. De meegeleverde broncode laat zien hoe u een document aan het einde van een ander document kunt invoegen terwijl de bronopmaak behouden blijft.

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

## Stap 3: Initialiseer DocumentBuilder

 Maak een nieuw exemplaar van de`DocumentBuilder` class en geef het doeldocument door als parameter.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Stap 4: Plaats de DocumentBuilder

Verplaats de`DocumentBuilder` naar het einde van het document met behulp van de`MoveToDocumentEnd` methode. Voeg een pagina-einde in om de bestaande inhoud van het ingevoegde document te scheiden.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Stap 5: Voeg het brondocument in

 Gebruik de`InsertDocument` werkwijze van de`DocumentBuilder` class om het brondocument in het doeldocument in te voegen. Stel de importformaatmodus in op`ImportFormatMode.KeepSourceFormatting` om de bronopmaak te behouden.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 6: Sla het gewijzigde document op

Sla ten slotte het gewijzigde bestemmingsdocument op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Hiermee is de implementatie voltooid van het invoegen van een document in een ander document met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor Insert Document With Builder met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```