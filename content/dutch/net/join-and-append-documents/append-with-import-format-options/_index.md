---
title: Voeg toe met importformaatopties
linktitle: Voeg toe met importformaatopties
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een document met importindelingsopties kunt toevoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/append-with-import-format-options/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET kunt gebruiken om de inhoud van het ene document aan het andere toe te voegen met opties voor importindelingen. De meegeleverde broncode laat zien hoe u de bron- en doeldocumenten opent, opties voor importindelingen specificeert en het brondocument aan het doeldocument toevoegt.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

-  Aspose.Words voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van[Aspose.Releases]https://releases.aspose.com/words/net/ of gebruik NuGet-pakketbeheer om het te installeren.
- Een documentmappad waar de bron- en doeldocumenten zich bevinden.

## Stap 2: Open de bron- en doeldocumenten

 Open de bron- en doeldocumenten met behulp van de`Document` klasse constructeur. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Stap 3: Geef de importformaatopties op

 Maak een exemplaar van de`ImportFormatOptions` class om de importformaatopties op te geven. In dit voorbeeld gebruiken we de`KeepSourceNumbering` eigenschap om ervoor te zorgen dat nummering uit het brondocument wordt gebruikt als er conflicten zijn met het doeldocument.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Stap 4: Voeg het brondocument toe aan het doeldocument

 Gebruik de`AppendDocument` methode van het doeldocument om het brondocument toe te voegen. Doorgang`ImportFormatMode.UseDestinationStyles` als de tweede parameter om de stijlen en opmaak van het doeldocument te gebruiken.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Stap 5: Sla het bestemmingsdocument op

 Sla ten slotte het gewijzigde bestemmingsdocument op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Hiermee is de implementatie voltooid van het toevoegen van een document met importformaatopties met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor Toevoegen met importformaatopties met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Specificeer dat als de nummering in bron- en doeldocumenten botst,
	//dan wordt de nummering uit het brondocument gebruikt.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```