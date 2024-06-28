---
title: Negeer tekst in velden
linktitle: Negeer tekst in velden
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de functie 'Tekst in velden negeren' van Aspose.Words voor .NET gebruikt.
type: docs
weight: 10
url: /nl/net/find-and-replace-text/ignore-text-inside-fields/
---
In dit artikel zullen we de bovenstaande C#-broncode verkennen om te begrijpen hoe u de functie Tekst binnen velden negeren in de Aspose.Words voor .NET-bibliotheek kunt gebruiken. Deze functie is handig als we de tekst in de velden willen negeren bij het manipuleren van documenten.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: Een nieuw document maken

 Voordat we tekst in velden gaan manipuleren, moeten we een nieuw document maken met Aspose.Words voor .NET. Dit kan gedaan worden door het instantiëren van een`Document` voorwerp:

```csharp
Document doc = new Document();
```

## Stap 2: Een veld met tekst erin invoegen

 Zodra we een document hebben, kunnen we een veld met tekst erin invoegen met behulp van a`DocumentBuilder` voorwerp. Om bijvoorbeeld een veld "INCLUDETEXT" in te voegen met de tekst "Tekst in veld", kunnen we de`InsertField` methode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## Stap 3: Gebruik de functie Tekst in velden negeren

 Om tekst in velden bij volgende bewerkingen te negeren, kunnen we a gebruiken`FindReplaceOptions` bezwaar maken en instellen`IgnoreFields`eigendom aan`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## Stap 4: Reguliere expressies gebruiken voor zoeken en vervangen

Om zoek- en vervangbewerkingen op de tekst van het document uit te voeren, zullen we reguliere expressies gebruiken. In ons voorbeeld zoeken we naar alle exemplaren van de letter "e" en vervangen we deze door een asterisk "* ". We zullen .NET's gebruiken`Regex` klasse hiervoor:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Stap 5: De gewijzigde documentuitvoer bekijken

 Na het toepassen van zoeken en vervangen kunnen we de gewijzigde inhoud van het document weergeven met behulp van de`GetText` methode:

```csharp
Console.WriteLine(doc.GetText());
```

## Stap 6: Opties wijzigen om velden op te nemen

 we nemen de tekst in de velden op in het uitvoerresultaat, we kunnen de opties wijzigen om de velden niet te negeren. Hiervoor stellen we de`IgnoreFields`eigendom aan`false`:

```csharp
options.IgnoreFields = false;
```

## Stap 7: Het gewijzigde document met de velden weergeven

Nadat we de opties hebben gewijzigd, kunnen we het zoeken en vervangen opnieuw uitvoeren om het resultaat te krijgen met de tekst in de opgenomen velden:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Voorbeeldbroncode voor het negeren van tekst in velden met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om het gebruik van de functie Ignore Text Inside Fields met Aspose.Words voor .NET te demonstreren:

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Veld invoegen met tekst erin.
	builder.InsertField("INCLUDETEXT", "Text in field");
	
	FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
	
	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreFields = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
  
```

## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de functie Tekst binnen velden negeren in Aspose.Words voor .NET kunt gebruiken. We volgden een stapsgewijze handleiding om een document te maken, een veld met tekst erin in te voegen, de functie Tekst in velden negeren te gebruiken, zoek- en vervangingsbewerkingen uit te voeren met reguliere expressies en het gewijzigde document weer te geven.

### Veelgestelde vragen

#### Vraag: Wat is de functie "Tekst in velden negeren" in Aspose.Words voor .NET?

A: Met de functie "Tekst in velden negeren" in Aspose.Words voor .NET kunt u opgeven of de tekst in velden moet worden genegeerd tijdens bepaalde bewerkingen, zoals het zoeken en vervangen van tekst. Wanneer deze functie is ingeschakeld, wordt er tijdens bewerkingen geen rekening gehouden met de tekst in de velden.

#### Vraag: Hoe kan ik een nieuw document maken met Aspose.Words voor .NET?

 A: Om een nieuw document te maken met Aspose.Words voor .NET, kunt u een`Document` voorwerp. Hier is een voorbeeld van C#-code om een nieuw document te maken:

```csharp
Document doc = new Document();
```

#### Vraag: Hoe kan ik een veld met tekst in een document invoegen met Aspose.Words voor .NET?

 A: Zodra u een document heeft, kunt u een veld met tekst erin invoegen met behulp van a`DocumentBuilder` voorwerp. Als u bijvoorbeeld een veld "INCLUDETEXT" wilt invoegen met de tekst "Tekst in veld", kunt u de`InsertField` methode:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### Vraag: Hoe kan ik tekst in velden in Aspose.Words voor .NET negeren?

 A: Om tekst in velden te negeren tijdens volgende bewerkingen, kunt u een`FindReplaceOptions` bezwaar maken en instellen`IgnoreFields`eigendom aan`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

#### Vraag: Hoe kan ik zoeken en vervangen met reguliere expressies in Aspose.Words voor .NET?

 A: Om zoek- en vervangbewerkingen uit te voeren op de tekst van het document met behulp van reguliere expressies, kunt u .NET gebruiken`Regex` klas. Als u bijvoorbeeld wilt zoeken naar alle exemplaren van de letter 'e' en deze wilt vervangen door een asterisk '* ", kunt u een`Regex` object en gebruik het met de`Replace` methode:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Vraag: Hoe kan ik de gewijzigde uitvoer van het document bekijken in Aspose.Words voor .NET?

 A: Nadat u zoek- en vervangbewerkingen hebt toegepast, kunt u de gewijzigde inhoud van het document bekijken met behulp van de`GetText` methode:

```csharp
Console.WriteLine(doc.GetText());
```

#### Vraag: Hoe kan ik de velden opnemen in het uitvoerresultaat in Aspose.Words voor .NET?

 A: Om de tekst in de velden in het uitvoerresultaat op te nemen, kunt u de opties zo wijzigen dat de velden niet worden genegeerd. Hiervoor kunt u de`IgnoreFields` eigendom van de`FindReplaceOptions` bezwaar tegen`false`:

```csharp
options.IgnoreFields = false;
```

#### Vraag: Hoe kan ik het gewijzigde document met de velden in Aspose.Words voor .NET weergeven?

A: Nadat u de opties heeft gewijzigd om velden op te nemen, kunt u het zoeken en vervangen opnieuw uitvoeren om het resultaat te krijgen met de tekst binnen de velden:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```