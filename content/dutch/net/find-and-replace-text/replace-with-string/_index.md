---
title: Vervangen door tekenreeks
linktitle: Vervangen door tekenreeks
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u tekst vervangt door een tekenreeks in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/find-and-replace-text/replace-with-string/
---
In dit artikel zullen we de bovenstaande C#-broncode verkennen om te begrijpen hoe u de functie Replace With String in de Aspose.Words voor .NET-bibliotheek kunt gebruiken. Met deze functie kunt u tekstvervanging uitvoeren op basis van een specifieke tekenreeks in een Word-document.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: Een nieuw document maken

 Voordat we tekenreeksvervanging gaan gebruiken, moeten we een nieuw document maken met Aspose.Words voor .NET. Dit kan gedaan worden door het instantiëren van een`Document` voorwerp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Stap 2: Voeg tekst in het document in

 Zodra we een document hebben, kunnen we tekst invoegen met behulp van a`DocumentBuilder` voorwerp. In ons voorbeeld gebruiken we de`Writeln` methode om de zinsnede "triest gek slecht" in te voegen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Stap 3: Vervang door een string

 Wij gebruiken de`Range.Replace`methode om tekst te vervangen door een tekenreeks. In ons voorbeeld vervangen we alle exemplaren van het woord 'verdrietig' door 'slecht' met behulp van de`FindReplaceOptions` optie met de`FindReplaceDirection.Forward` zoekrichting:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Stap 4: Het bewerkte document opslaan

Ten slotte slaan we het gewijzigde document op in een opgegeven map met behulp van de`Save` methode:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Voorbeeldbroncode voor Replace With String met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om het gebruik van vervangen door een tekenreeks met Aspose.Words voor .NET te illustreren:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de functie Replace With String van Aspose.Words voor .NET kunt gebruiken. We volgden een stapsgewijze handleiding om een document te maken, tekst in te voegen, te vervangen door een tekenreeks en het gewijzigde document op te slaan.

### Veelgestelde vragen

#### Vraag: Wat is de functie "Vervangen door string" in Aspose.Words voor .NET?

A: Met de functie "Vervangen door tekenreeks" in Aspose.Words voor .NET kunt u tekstvervanging uitvoeren op basis van een specifieke tekenreeks in een Word-document. Hiermee kunt u voorkomens van een bepaalde tekenreeks vinden en deze vervangen door een andere opgegeven tekenreeks.

#### Vraag: Hoe kan ik een nieuw document maken met Aspose.Words voor .NET?

 A: Om een nieuw document te maken met Aspose.Words voor .NET, kunt u een`Document` voorwerp. Hier is een voorbeeld van C#-code om een nieuw document te maken:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### Vraag: Hoe kan ik tekst in een document invoegen met Aspose.Words voor .NET?

 A: Zodra u een document heeft, kunt u tekst invoegen met behulp van a`DocumentBuilder` voorwerp. In Aspose.Words voor .NET kunt u verschillende methoden van de .NET gebruiken`DocumentBuilder` klasse om tekst op verschillende locaties in te voegen. U kunt bijvoorbeeld gebruik maken van de`Writeln` methode om tekst op een nieuwe regel in te voegen. Hier is een voorbeeld:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### Vraag: Hoe kan ik tekstvervanging uitvoeren door een tekenreeks in Aspose.Words voor .NET?

 A: Om tekstvervanging door een string uit te voeren in Aspose.Words voor .NET, kunt u de`Range.Replace` methode en specificeer de tekenreeks die moet worden vervangen en de tekenreeks waarmee deze moet worden vervangen. Deze methode voert een eenvoudige tekstmatch uit en vervangt alle exemplaren van de opgegeven tekenreeks. Hier is een voorbeeld:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### Vraag: Kan ik hoofdlettergevoelige tekstvervanging uitvoeren met de functie "Replace With String" in Aspose.Words voor .NET?

A: Ja, de functie "Vervangen door String" in Aspose.Words voor .NET is standaard hoofdlettergevoelig. Dit betekent dat alleen tekst wordt vervangen die qua hoofdlettergebruik exact overeenkomt met de opgegeven tekenreeks. Als u een hoofdletterongevoelige vervanging wilt uitvoeren, kunt u de te vervangen tekst en de vervangende tekenreeks wijzigen zodat deze dezelfde hoofdlettergrootte heeft, of u kunt andere technieken gebruiken, zoals reguliere expressies.

#### Vraag: Kan ik meerdere exemplaren van een tekenreeks in een document vervangen met behulp van de functie "Vervangen door tekenreeks" in Aspose.Words voor .NET?

 A: Ja, u kunt meerdere exemplaren van een tekenreeks in een document vervangen met behulp van de functie "Vervangen door tekenreeks" in Aspose.Words voor .NET. De`Range.Replace` methode vervangt alle exemplaren van de opgegeven tekenreeks in de inhoud van het document.

#### Vraag: Zijn er beperkingen of overwegingen bij het gebruik van de functie "Replace With String" in Aspose.Words voor .NET?

A: Wanneer u de functie "Vervangen door tekenreeks" in Aspose.Words voor .NET gebruikt, is het belangrijk om op de hoogte te zijn van de context en ervoor te zorgen dat de vervanging alleen wordt toegepast waar de bedoeling is. Zorg ervoor dat de zoekreeks niet op ongewenste plaatsen verschijnt, zoals in andere woorden of als onderdeel van speciale opmaak. Houd bovendien rekening met de gevolgen voor de prestaties bij het verwerken van woorden met grote documenten of frequente vervangingen.

#### Vraag: Kan ik strings met verschillende lengtes vervangen met behulp van de functie "Replace With String" in Aspose.Words voor .NET?

A: Ja, je kunt strings met verschillende lengtes vervangen met behulp van de functie "Replace With String" in Aspose.Words voor .NET. De vervangende tekenreeks kan elke lengte hebben en vervangt de exacte overeenkomst met de zoekreeks. Het document wordt dienovereenkomstig aangepast aan de nieuwe tekenreekslengte.