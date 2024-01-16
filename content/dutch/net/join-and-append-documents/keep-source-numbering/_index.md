---
title: Behoud de bronnummering
linktitle: Behoud de bronnummering
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een document kunt toevoegen met behoud van de opmaak van de bronnummering in Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/keep-source-numbering/
---

In deze zelfstudie wordt uitgelegd hoe u een brondocument aan een doeldocument kunt toevoegen met behoud van de oorspronkelijke nummeringsopmaak van genummerde alinea's met behulp van Aspose.Words voor .NET.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

-  Aspose.Words voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van[Aspose.Releases]https://releases.aspose.com/words/net/ of gebruik NuGet-pakketbeheer om het te installeren.
- Een documentmappad waar de bron- en doeldocumenten worden opgeslagen.

## Stap 2: Maak de bestemmings- en brondocumenten

 Maak exemplaren van`Document` voor de bestemmings- en brondocumenten.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Stap 3: Behoud de bronnummering bij het importeren

 Als u de nummeringsopmaak van genummerde alinea's uit het brondocument wilt behouden, maakt u een exemplaar van`ImportFormatOptions` En instellen`KeepSourceNumbering` naar`true` . Gebruik een`NodeImporter` om knooppunten van het brondocument naar het bestemmingsdocument te importeren, met specificatie`ImportFormatMode.KeepSourceFormatting` en de`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Stap 4: Importeer en voeg alinea's toe

Blader door de alinea's in het brondocument en importeer elke alinea in het doeldocument met behulp van de`importer`. Voeg de geïmporteerde knooppunten toe aan de hoofdtekst van het doeldocument.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Stap 5: Sla het gewijzigde document op

 Sla het gewijzigde document op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Hiermee is de implementatie voltooid van het toevoegen van een brondocument aan een doeldocument, terwijl de oorspronkelijke nummeringsopmaak behouden blijft met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor Bronnummering behouden met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Behoud de opmaak van de bronlijst bij het importeren van genummerde alinea's.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```