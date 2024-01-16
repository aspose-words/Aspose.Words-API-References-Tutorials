---
title: Koptekst-voettekstinhoud verwijderen
linktitle: Koptekst-voettekstinhoud verwijderen
second_title: Aspose.Words-API voor documentverwerking
description: In deze zelfstudie leert u hoe u kop- en voettekstinhoud uit een Word-document verwijdert met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-section/delete-header-footer-content/
---

In deze zelfstudie laten we u zien hoe u kop- en voettekstinhoud uit een Word-document verwijdert met behulp van de Aspose.Words-bibliotheek voor .NET. Het verwijderen van inhoud uit kop- en voetteksten kan handig zijn als u deze elementen uit uw document opnieuw wilt instellen of verwijderen. We nemen u stap voor stap mee om u te helpen de code in uw .NET-project te begrijpen en te implementeren.

## Vereisten
Zorg ervoor dat u over de volgende items beschikt voordat u begint:
- Een praktische kennis van de programmeertaal C#
- De Aspose.Words-bibliotheek voor .NET die in uw project is geïnstalleerd
- Een Word-document met kop- en voetteksten die u wilt verwijderen

## Stap 1: Definieer de documentmap
 Eerst moet u het mappad instellen op de locatie van uw Word-document. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het juiste pad.

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Laad het document en ga naar de sectie
 Vervolgens laden we het Word-document in een exemplaar van het`Document` klas. We openen het eerste deel van het document met index 0.

```csharp
// Laad het document
Document doc = new Document(dataDir + "Document.docx");

// Toegang tot de sectie
Section section = doc.Sections[0];
```

## Stap 3: Verwijder kop- en voettekstinhoud
 Om de kop- en voettekstinhoud uit de sectie te verwijderen, gebruiken we de`ClearHeadersFooters` methode.

```csharp
section.ClearHeadersFooters();
```

### Voorbeeldbroncode voor het verwijderen van koptekst-voettekstinhoud met Aspose.Words voor .NET 

```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## Conclusie
In deze zelfstudie hebben we gezien hoe u de kop- en voettekstinhoud uit een Word-document kunt verwijderen met Aspose.Words voor .NET. Door inhoud uit kop- en voetteksten te verwijderen, kunt u die specifieke elementen uit uw document opnieuw instellen of verwijderen. U kunt deze functie gerust aanpassen en gebruiken volgens uw specifieke behoeften.

### Veelgestelde vragen over het verwijderen van koptekst-voettekstinhoud

#### Vraag: Hoe kan ik de documentmap instellen in Aspose.Words voor .NET?

 A: Om het pad in te stellen naar de map die uw documenten bevat, moet u vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het juiste pad. Hier leest u hoe u het moet doen:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### Vraag: Hoe kan ik een document laden en de sectie openen in Aspose.Words voor .NET?

 A: Om het Word-document in een exemplaar van het`Document` klas gebeld`doc` en toegang krijgt tot het eerste gedeelte van het document met index 0, kunt u de volgende code gebruiken:

```csharp
// Laad het document
Document doc = new Document(dataDir + "Document.docx");

// Toegang tot de sectie
Section section = doc.Sections[0];
```

#### Vraag: Hoe kan ik kop- en voettekstinhoud verwijderen in Aspose.Words voor .NET?

 A: Om de kop- en voettekstinhoud uit de sectie te verwijderen, kunt u de`ClearHeadersFooters` methode:

```csharp
section.ClearHeadersFooters();
```

#### Vraag: Hoe kan ik het gewijzigde document opslaan in Aspose.Words voor .NET?

A: Nadat u de kop- en voettekstinhoud heeft verwijderd, kunt u het gewijzigde document opslaan in een bestand met behulp van de volgende code:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```