---
title: Negeer tekstvakken
linktitle: Negeer tekstvakken
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een document kunt toevoegen terwijl u de opmaak van tekstvakken negeert met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/ignore-text-boxes/
---

In deze tutorial wordt uitgelegd hoe u Aspose.Words voor .NET kunt gebruiken om een document toe te voegen terwijl de opmaak van tekstvakken behouden blijft. De meegeleverde broncode demonstreert hoe u de importformaatopties kunt instellen om tekstvakken op te nemen tijdens het toevoegproces.

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

## Stap 3: Stel importformaatopties in

 Maak een exemplaar van de`ImportFormatOptions` klasse en stel de`IgnoreTextBoxes`eigendom aan`false`. Dit zorgt ervoor dat de tekstvakken worden opgenomen tijdens het toevoegproces, terwijl hun opmaak behouden blijft.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Stap 4: Voeg de inhoud van het tekstvak toe

 Maak een`NodeImporter`object en gebruik het om tekstvakknooppunten van het brondocument naar het doeldocument te importeren. Doorloop elke alinea in het brondocument en importeer deze in het doeldocument.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Stap 5: Sla het bestemmingsdocument op

Sla ten slotte het gewijzigde bestemmingsdocument op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Hiermee is de implementatie van het toevoegen van een document voltooid, terwijl de opmaak van de tekstvakken behouden blijft met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor het negeren van tekstvakken met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Houd de opmaak van de brontekstvakken bij het importeren behouden.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```