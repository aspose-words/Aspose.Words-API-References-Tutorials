---
title: Word-documenten samenvoegen
linktitle: Documenten samenvoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u meerdere Word-documenten samenvoegt met Aspose.Words voor .NET. Deze krachtige API vereenvoudigt het samenvoegen van documenten, waardoor het efficiënt en eenvoudig wordt.
type: docs
weight: 10
url: /nl/net/split-document/merge-documents/
---

In deze zelfstudie laten we u zien hoe u meerdere Word-documenten kunt samenvoegen met behulp van de functie Documenten samenvoegen van Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en een samengevoegd document te krijgen met alle brondocumenten.

## Stap 1: Zoek naar documenten om samen te voegen

Voordat we de documenten samenvoegen, moeten we de brondocumenten lokaliseren die moeten worden samengevoegd. Hier is hoe:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Zoek naar documenten om samen te voegen.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Stap 2: Documenten samenvoegen

Nu zullen we de documenten één voor één samenvoegen om een definitief samengevoegd document te creëren. Hier is hoe:

```csharp
// Open het eerste deel van het resulterende document.
Document sourceDoc = new Document(sourceDocumentPath);

// Maak een nieuw resulterend document.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Voeg de documenten één voor één samen.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Voorbeeldbroncode voor het samenvoegen van documenten met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie Merge Documents van Aspose.Words voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Zoek documenten met behulp van samenvoegen.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Open het eerste deel van het resulterende document.
Document sourceDoc = new Document(sourceDocumentPath);

// Maak een nieuw resulterend document.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Voeg documentonderdelen één voor één samen.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## Conclusie

Gefeliciteerd! U hebt geleerd hoe u meerdere Word-documenten kunt samenvoegen met de functie Documenten samenvoegen van Aspose.Words voor .NET. Door de meegeleverde broncode te volgen, kunt u afzonderlijke documenten combineren tot één samengevoegd document, terwijl de opmaak van elk brondocument behouden blijft.

Het samenvoegen van documenten kan handig zijn als u informatie uit meerdere bronnen wilt consolideren of een uniform document wilt maken van afzonderlijke delen. Aspose.Words voor .NET biedt een krachtige API die het samenvoegen van documenten vereenvoudigt, waardoor het efficiënt en eenvoudig wordt.

Ontdek gerust andere functies van Aspose.Words voor .NET om uw documentverwerkingsmogelijkheden te verbeteren en uw workflow te stroomlijnen.

### Veelgestelde vragen

#### Hoe kan ik documenten met verschillende opmaak samenvoegen?

 Bij het samenvoegen van documenten biedt Aspose.Words voor .NET de mogelijkheid om de opmaak van elk brondocument te behouden. Door gebruik te maken van de`ImportFormatMode.KeepSourceFormatting` optie behoudt het samengevoegde document de opmaak van de originele documenten. Als u consistente opmaak wilt toepassen op het samengevoegde document, kunt u de opmaak wijzigen met behulp van de Aspose.Words API nadat u de documenten hebt samengevoegd.

#### Kan ik documenten in verschillende formaten samenvoegen?

Ja, Aspose.Words voor .NET ondersteunt het samenvoegen van documenten in verschillende formaten, waaronder DOCX, DOC, RTF en meer. U kunt documenten met verschillende formaten in de Aspose.Words API laden en ze samenvoegen tot één document, ongeacht hun originele formaten.

#### Kan ik documenten met complexe structuren, zoals tabellen en afbeeldingen, samenvoegen?

Absoluut! Aspose.Words voor .NET kan documenten met complexe structuren samenvoegen, waaronder tabellen, afbeeldingen, kop- en voetteksten en meer. De API verzorgt het samenvoegproces terwijl de integriteit en lay-out van de inhoud in elk document behouden blijft.

#### Is het mogelijk om documenten met verschillende paginarichtingen of formaten samen te voegen?

Ja, Aspose.Words voor .NET verwerkt documenten met verschillende paginarichtingen of formaten tijdens het samenvoegproces. Het resulterende samengevoegde document is geschikt voor de verschillende paginarichtingen en formaten van de brondocumenten.