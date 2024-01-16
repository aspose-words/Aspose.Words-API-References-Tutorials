---
title: Negeer koptekst en voettekst
linktitle: Negeer koptekst en voettekst
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een document kunt toevoegen terwijl u de inhoud van de kop- en voettekst negeert met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/ignore-header-footer/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET kunt gebruiken om een document toe te voegen terwijl de kop- en voettekstinhoud wordt genegeerd. De meegeleverde broncode laat zien hoe u de importformaatopties instelt om de kop- en voettekst uit te sluiten tijdens het toevoegproces.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

-  Aspose.Words voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van[Aspose.Releases]https://releases.aspose.com/words/net/ of gebruik NuGet-pakketbeheer om het te installeren.
- Een documentmappad waar de bron- en doeldocumenten zich bevinden.

## Stap 2: Open de bron- en doeldocumenten

 Open de bron- en doeldocumenten met behulp van de`Document` klasse constructeur. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Stap 3: Stel importformaatopties in

 Maak een exemplaar van de`ImportFormatOptions` klasse en stel de`IgnoreHeaderFooter`eigendom aan`false`. Dit zorgt ervoor dat de kop- en voettekstinhoud wordt opgenomen tijdens het toevoegproces.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Stap 4: Voeg het brondocument toe aan het doeldocument

 Gebruik de`AppendDocument` methode van het doeldocument om het brondocument toe te voegen. Doorgang`ImportFormatMode.KeepSourceFormatting` als tweede parameter en de importformaatopties als derde parameter.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Stap 5: Sla het bestemmingsdocument op

 Sla ten slotte het gewijzigde bestemmingsdocument op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Hiermee is de implementatie voltooid van het toevoegen van een document terwijl de kop- en voettekstinhoud wordt genegeerd met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor het negeren van kop- en voettekst met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```