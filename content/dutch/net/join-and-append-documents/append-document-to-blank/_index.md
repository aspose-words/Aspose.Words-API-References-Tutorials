---
title: Document aan blanco toevoegen
linktitle: Document aan blanco toevoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een document toevoegt aan een leeg doeldocument in Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/append-document-to-blank/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET kunt gebruiken om de inhoud van één document aan een leeg doeldocument toe te voegen. De meegeleverde broncode laat zien hoe u een nieuw document maakt, de inhoud ervan verwijdert en vervolgens het brondocument eraan toevoegt.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

-  Aspose.Words voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van[Aspose.Releases]https://releases.aspose.com/words/net/ of gebruik NuGet-pakketbeheer om het te installeren.
- Een documentmappad waar de bron- en doeldocumenten zich bevinden.

## Stap 2: Maak een nieuw bestemmingsdocument

 Maak een nieuwe`Document` object voor het bestemmingsdocument.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Stap 3: Verwijder bestaande inhoud uit het doeldocument

 Om een schoon bestemmingsdocument te garanderen, verwijdert u alle bestaande inhoud uit het document met behulp van de`RemoveAllChildren` methode.

```csharp
dstDoc.RemoveAllChildren();
```

## Stap 4: Voeg het brondocument toe aan het doeldocument

 Voeg de inhoud van het brondocument toe aan het doeldocument met behulp van de`AppendDocument` methode met`ImportFormatMode.KeepSourceFormatting` keuze.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 5: Sla het bestemmingsdocument op

Sla ten slotte het gewijzigde bestemmingsdocument op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Hiermee is de implementatie voltooid van het toevoegen van een document aan een leeg doeldocument met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor Document toevoegen aan blanco met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// Het doeldocument is niet leeg, waardoor er vaak een lege pagina verschijnt vóór het toegevoegde document.
	// Dit komt doordat het basisdocument een leeg gedeelte heeft en het nieuwe document op de volgende pagina wordt gestart.
	// Verwijder alle inhoud uit het doeldocument voordat u deze toevoegt.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```