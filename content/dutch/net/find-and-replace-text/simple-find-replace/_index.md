---
title: Eenvoudige tekst zoeken en vervangen in Word
linktitle: Eenvoudige tekst zoeken en vervangen in Word
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u eenvoudig tekst kunt zoeken en vervangen in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/find-and-replace-text/simple-find-replace/
---
In dit artikel zullen we de bovenstaande C#-broncode onderzoeken om te begrijpen hoe u de eenvoudige tekst Zoeken en vervangen kunt gebruiken in de Aspose.Words voor .NET-bibliotheek. Met deze functie kunt u eenvoudige tekstvervanging uitvoeren door naar een specifieke reeks tekens te zoeken en deze te vervangen door een andere reeks tekens in een Word-document.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: Een nieuw document maken

 Voordat we eenvoudig zoeken en vervangen gaan gebruiken, moeten we een nieuw document maken met Aspose.Words voor .NET. Dit kan gedaan worden door het instantiëren van een`Document` voorwerp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Stap 2: Voeg tekst in het document in

 Zodra we een document hebben, kunnen we tekst invoegen met behulp van a`DocumentBuilder` voorwerp. In ons voorbeeld gebruiken we de`Writeln` methode om de zinsnede "Hallo_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Stap 3: Eenvoudige tekstvervanging

 Wij gebruiken de`Range.Replace` methode om eenvoudige tekstvervanging uit te voeren. In ons voorbeeld vervangen we alle exemplaren van de string "_ClientName_ " met "James Bond" met behulp van de`FindReplaceOptions` optie met de`FindReplaceDirection.Forward` zoekrichting:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Stap 4: Het bewerkte document opslaan

Ten slotte slaan we het gewijzigde document op in een opgegeven map met behulp van de`Save` methode:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Voorbeeldbroncode voor Simple Find Replace met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om het gebruik van eenvoudig zoeken en vervangen met Aspose.Words voor .NET te demonstreren:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Sla het gewijzigde document op
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de Simple Find Replace-functie van Aspose.Words voor .NET kunt gebruiken. We volgden een stapsgewijze handleiding om een document te maken, tekst in te voegen, eenvoudige tekstvervanging uit te voeren en het bewerkte document op te slaan.

### Veelgestelde vragen

#### Vraag: Wat is de functie voor het zoeken en vervangen van eenvoudige tekst in Aspose.Words voor .NET?

A: Met de functie Eenvoudig zoeken en vervangen van tekst in Aspose.Words voor .NET kunt u eenvoudige tekstvervanging uitvoeren in een Word-document. Hiermee kunt u naar een specifieke tekenreeks zoeken en deze vervangen door een andere tekenreeks. Dit kan handig zijn als u globale wijzigingen in een document wilt aanbrengen, zoals het vervangen van namen, datums of andere informatie.

#### Vraag: Hoe maak ik een nieuw document in Aspose.Words voor .NET?

 A: Voordat u de functie Eenvoudig zoeken en vervangen van tekst gebruikt, moet u een nieuw document maken met Aspose.Words voor .NET. Dit kan gedaan worden door het instantiëren van een`Document` voorwerp. Hier is een voorbeeldcode om een nieuw document te maken:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Vraag: Hoe kan ik tekst in een document invoegen met Aspose.Words voor .NET?

 A: Zodra u een document heeft, kunt u tekst invoegen met behulp van a`DocumentBuilder` voorwerp. In ons voorbeeld gebruiken we de`Writeln` methode om de zinsnede "Hallo_CustomerName_:":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### Vraag: Hoe voer ik eenvoudige tekstvervanging uit in een document met Aspose.Words voor .NET?

 A: Om een eenvoudige tekstvervanging uit te voeren, kunt u de`Range.Replace` methode. In ons voorbeeld vervangen we alle exemplaren van de string "_ClientName_ " met "James Bond" met behulp van de`FindReplaceOptions` optie met de`FindReplaceDirection.Forward` zoekrichting:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### Vraag: Hoe kan ik een bewerkt document opslaan in Aspose.Words voor .NET?

 A: Nadat u de tekstvervanging heeft uitgevoerd, kunt u het gewijzigde document opslaan in een opgegeven map met behulp van de`Save` methode:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```