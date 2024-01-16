---
title: Toegang tot bladwijzers in Word-document
linktitle: Toegang tot bladwijzers in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u bladwijzers in een Word-document kunt openen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/access-bookmarks/
---

In dit artikel zullen we de bovenstaande C#-broncode verkennen om te begrijpen hoe u de Access Bookmarks-functie kunt gebruiken in de Aspose.Words voor .NET-bibliotheek. Deze functie biedt toegang tot specifieke bladwijzers in een Word-document.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: Het document laden

 Voordat we toegang krijgen tot bladwijzers, moeten we een Word-document laden met Aspose.Words voor .NET. Dit kan gedaan worden door het instantiëren van een`Document` object dat het documentbestandspad specificeert:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Stap 2: Toegang tot bladwijzers

Zodra het document is geladen, hebben we toegang tot de bladwijzers in het document. Er zijn twee manieren om toegang te krijgen tot bladwijzers: via index en via naam.

- Toegang via index: In ons voorbeeld gebruiken we index 0 om toegang te krijgen tot de eerste bladwijzer van het document:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Toegang op naam: In ons voorbeeld gebruiken we de naam "MyBookmark3" om toegang te krijgen tot een specifieke bladwijzer in het document:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

### Voorbeeldbroncode voor Access Bookmarks met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om de toegang tot bladwijzers aan te tonen met behulp van Aspose.Words voor .NET:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");
	
	// Per index:
	Bookmark bookmark1 = doc.Range.Bookmarks[0];
	// Bij naam:
	Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
   
```

## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de Access Bookmarks-functie van Aspose.Words voor .NET kunt gebruiken. We volgden een stapsgewijze handleiding om een document te uploaden en toegang te krijgen tot bladwijzers met behulp van index en naam.

### Veelgestelde vragen over toegang tot bladwijzers in een Word-document

#### Vraag: Hoe kan ik een Word-document uploaden met Aspose.Words voor .NET?

 A: Om een Word-document te laden met Aspose.Words voor .NET, kunt u een`Document`object door het bestandspad van het document op te geven. Hier is een voorbeeldcode:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

#### Vraag: Hoe krijg ik toegang tot bladwijzers in een Word-document?

 A: U kunt bladwijzers in een Word-document openen met behulp van de`Bookmarks` eigendom van de`Range` voorwerp. U kunt bladwijzers openen op index of op naam. Hier is een voorbeeldcode:

- Toegang via index:

```csharp
Bookmark bookmark1 = doc.Range.Bookmarks[0];
```

- Toegang op naam:

```csharp
Bookmark bookmark2 = doc.Range.Bookmarks["MyBookmark3"];
```

#### Vraag: Welke bibliotheek is vereist om de functie voor bladwijzertoegang in Aspose.Words voor .NET te gebruiken?

A: Om de functie voor bladwijzertoegang in Aspose.Words voor .NET te gebruiken, hebt u de Aspose.Words-bibliotheek nodig. Zorg ervoor dat deze bibliotheek in uw .NET-ontwikkelomgeving is geïnstalleerd.

#### Vraag: Zijn er andere manieren om toegang te krijgen tot bladwijzers in een Word-document?

 A: Ja, naast toegang tot bladwijzers via index of naam kunt u ook door alle bladwijzers in het document bladeren met behulp van een lus. U kunt het totale aantal bladwijzers in het document verkrijgen met behulp van de`Count` eigendom van de`Bookmarks` verzameling. Vervolgens kunt u elke bladwijzer openen via de index. Hier is een voorbeeldcode:

```csharp
int bookmarkCount = doc.Range.Bookmarks.Count;

for (int i = 0; i < bookmarkCount; i++)
{
     Bookmark bookmark = doc.Range.Bookmarks[i];
     // Doe iets met de bladwijzer...
}
```