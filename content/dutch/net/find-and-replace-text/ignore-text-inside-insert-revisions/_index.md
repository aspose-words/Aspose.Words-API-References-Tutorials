---
title: Negeer tekst in invoegrevisies
linktitle: Negeer tekst in invoegrevisies
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de functie "Tekst in invoegrevisies negeren" van Aspose.Words voor .NET kunt gebruiken om invoegrevisies in Word-documenten te manipuleren.
type: docs
weight: 10
url: /nl/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

In dit artikel zullen we de bovenstaande C#-broncode verkennen om te begrijpen hoe u de functie Negeer tekst binnen invoegrevisies kunt gebruiken in de Aspose.Words voor .NET-bibliotheek. Deze functie is handig als we tekst in invoegrevisies willen negeren tijdens het manipuleren van documenten.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: Een nieuw document maken

 Voordat we beginnen met het manipuleren van tekst in invoegrevisies, moeten we een nieuw document maken met Aspose.Words voor .NET. Dit kan gedaan worden door het instantiëren van een`Document` voorwerp:

```csharp
Document doc = new Document();
```

## Stap 2: Voeg tekst in met revisietracking

 Zodra we een document hebben, kunnen we tekst invoegen met revisietracering met behulp van een`DocumentBuilder`voorwerp. Om bijvoorbeeld de tekst "Ingevoegd" in te voegen met revisietracking, kunnen we de`StartTrackRevisions`, `Writeln` En`StopTrackRevisions` methoden:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Stap 3: Voeg niet-beoordeelde tekst in

 Naast tekst met revisietracking kunnen we ook niet-gereviseerde tekst invoegen met behulp van de`DocumentBuilder` voorwerp. Om bijvoorbeeld de tekst "Tekst" zonder revisie in te voegen, kunnen we de`Write` methode:

```csharp
builder.Write("Text");
```

## Stap 4: Gebruik de functie Tekst negeren in revisies invoegen

 Om tekst in invoegrevisies bij volgende bewerkingen te negeren, kunnen we a`FindReplaceOptions` bezwaar maken en instellen`IgnoreInserted`eigendom aan`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Stap 5: Reguliere expressies gebruiken voor zoeken en vervangen

Om zoekbewerkingen en vervangingen op de documenttekst uit te voeren, zullen we reguliere expressies gebruiken. In ons voorbeeld zoeken we naar alle exemplaren van de letter "e" en vervangen we deze door een asterisk "* ". We zullen .NET's gebruiken`Regex` klasse hiervoor:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Stap 6: De gewijzigde documentuitvoer bekijken

 Na het toepassen van zoeken en vervangen kunnen we de gewijzigde inhoud van het document weergeven met behulp van de`GetText` methode:

```csharp
Console.WriteLine(doc.GetText());
```

## Stap 7: Opties wijzigen om invoegrevisies op te nemen

Als we de tekst in de invoegrevisies in het uitvoerresultaat willen opnemen, kunnen we de opties wijzigen zodat de invoegrevisies niet worden genegeerd. Hiervoor stellen we de`IgnoreInserted`eigendom aan`false`:

```csharp
options.IgnoreInserted = false;
```

## Stap 8: Het gewijzigde document bekijken met invoegrevisies

Nadat we de opties hebben gewijzigd, kunnen we het zoeken en vervangen opnieuw uitvoeren om het resultaat te krijgen met de tekst in de ingevoegde revisies:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Voorbeeldbroncode voor het negeren van tekst in invoegrevisies met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om het gebruik van de functie Ignore Text Inside Insert Revisions met Aspose.Words voor .NET te demonstreren:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Voeg tekst in met trackingrevisies.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Voeg niet-herziene tekst in.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de functie Negeer tekst binnen invoegrevisies kunt gebruiken in Aspose.Words voor .NET. We volgden een stapsgewijze handleiding voor het maken van een document, het invoegen van tekst met het bijhouden van revisies en niet-gereviseerde tekst, het gebruiken van de functie Tekst negeren in revisies invoegen, het uitvoeren van zoek- en vervangingsbewerkingen met reguliere expressies, en het weergeven van het gewijzigde document.

### Veelgestelde vragen

#### Vraag: Wat is de functie 'Tekst in invoegrevisies negeren' in Aspose.Words voor .NET?

A: Met de functie "Tekst in invoegrevisies negeren" in Aspose.Words voor .NET kunt u opgeven of de tekst in invoegrevisies moet worden genegeerd tijdens bepaalde bewerkingen, zoals het zoeken en vervangen van tekst. Wanneer deze functie is ingeschakeld, wordt er tijdens bewerkingen geen rekening gehouden met de tekst in de invoegrevisies.

#### Vraag: Hoe kan ik een nieuw document maken met Aspose.Words voor .NET?

 A: Om een nieuw document te maken met Aspose.Words voor .NET, kunt u een`Document` voorwerp. Hier is een voorbeeld van C#-code om een nieuw document te maken:

```csharp
Document doc = new Document();
```

#### Vraag: Hoe kan ik tekst invoegen met revisietracking in Aspose.Words voor .NET?

A: Zodra u een document heeft, kunt u tekst invoegen met revisietracering met behulp van a`DocumentBuilder` voorwerp. Als u bijvoorbeeld de tekst "Ingevoegd" wilt invoegen met revisietracking, kunt u de`StartTrackRevisions`, `Writeln` , En`StopTrackRevisions` methoden:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### Vraag: Hoe kan ik ongewijzigde tekst invoegen in Aspose.Words voor .NET?

 A: Naast tekst met revisietracering kunt u ook niet-gereviseerde tekst invoegen met behulp van de`DocumentBuilder` voorwerp. Als u bijvoorbeeld de tekst "Tekst" zonder revisie wilt invoegen, kunt u de`Write` methode:

```csharp
builder.Write("Text");
```

#### Vraag: Hoe kan ik tekst negeren in invoegrevisies in Aspose.Words voor .NET?

 A: Om tekst in invoegrevisies te negeren tijdens volgende bewerkingen, kunt u een`FindReplaceOptions` bezwaar maken en instellen`IgnoreInserted`eigendom aan`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
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

#### Vraag: Hoe kan ik de invoegrevisies opnemen in het uitvoerresultaat in Aspose.Words voor .NET?

 A: Om de tekst binnen de invoegrevisies op te nemen in het uitvoerresultaat, kunt u de opties zo wijzigen dat de invoegrevisies niet worden genegeerd. Hiervoor kunt u de`IgnoreInserted` eigendom van de`FindReplaceOptions` bezwaar tegen`false`:

```csharp
options.IgnoreInserted = false;
```

#### Vraag: Hoe kan ik het gewijzigde document met de invoegrevisies weergeven in Aspose.Words voor .NET?

A: Nadat u de opties hebt gewijzigd om invoegrevisies op te nemen, kunt u het zoeken en vervangen opnieuw uitvoeren om het resultaat te krijgen, inclusief de tekst in de invoegrevisies:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```