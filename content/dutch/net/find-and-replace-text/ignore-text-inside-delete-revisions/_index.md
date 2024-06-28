---
title: Negeer tekst binnenin en verwijder revisies
linktitle: Negeer tekst binnenin en verwijder revisies
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de functie 'Tekst in verwijder revisies negeren' van Aspose.Words voor .NET gebruikt.
type: docs
weight: 10
url: /nl/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

In dit artikel zullen we de bovenstaande C#-broncode onderzoeken om te begrijpen hoe u de functie 'Tekst negeren binnen verwijderingsrevisies' in de Aspose.Words voor .NET-bibliotheek kunt gebruiken. Deze functie is handig als we tekst in verwijderingsrevisies willen negeren bij het verwerken van woorden met documenten.

## Overzicht van de Aspose.Words voor .NET-bibliotheek

Voordat ik in de codedetails duik, wil ik eerst kort de Aspose.Words voor .NET-bibliotheek introduceren. Het is een krachtige bibliotheek waarmee u Word-documenten in .NET-toepassingen kunt maken, wijzigen en converteren. Het biedt veel geavanceerde functies voor tekstverwerking met documenten, inclusief revisiebeheer.

## De functie "Tekst in revisies verwijderen negeren" begrijpen

Met de functie "Tekst binnen verwijderrevisies negeren" in Aspose.Words voor .NET kunt u opgeven of tekst in verwijderrevisies moet worden genegeerd tijdens bepaalde bewerkingen, zoals het zoeken en vervangen van tekst. Wanneer deze functie is ingeschakeld, wordt tijdens bewerkingen geen rekening gehouden met verwijderde tekst in revisies.

## Stap 1: Een nieuw document maken met Aspose.Words voor .NET

 Voordat we tekst in een document gaan manipuleren, moeten we een nieuw document maken met Aspose.Words voor .NET. Dit kan worden gedaan door het instantiëren van a`Document` voorwerp:

```csharp
Document doc = new Document();
```

## Stap 2: Niet-herziene tekst in het document invoegen

 Zodra we een document hebben, kunnen we niet-beoordeelde tekst invoegen met behulp van a`DocumentBuilder` voorwerp. Om bijvoorbeeld de tekst "Verwijderde tekst" in te voegen, kunnen we de`Writeln` En`Write` methoden:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Stap 3: Een alinea verwijderen met trackingrevisies

Ter illustratie van het gebruik van de functie "Tekst negeren binnen revisies verwijderen" verwijderen we een alinea uit het document met behulp van het bijhouden van revisies. Hierdoor kunnen we zien hoe deze functie latere bewerkingen beïnvloedt.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Stap 4: De functie "Tekst negeren in revisies verwijderen" toepassen

 Nu we ons document hebben voorbereid door een alinea te verwijderen, kunnen we de functie "Tekst negeren binnen revisies verwijderen" inschakelen met behulp van een`FindReplaceOptions` voorwerp. Wij zullen de`IgnoreDeleted`eigendom aan`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Stap 5: Reguliere expressies gebruiken voor zoeken en vervangen

Om zoek- en vervangbewerkingen op de tekst van het document uit te voeren, zullen we reguliere expressies gebruiken. In ons voorbeeld zoeken we naar alle exemplaren van de letter "e" en vervangen we deze door een asterisk "* ". .NET`Regex` Hiervoor wordt klasse gebruikt:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Stap 6: De gewijzigde documentuitvoer weergeven

 Na het toepassen van zoeken en vervangen kunnen we de gewijzigde inhoud van het document weergeven met behulp van de`GetText` methode:

```csharp
Console.WriteLine(doc.GetText());
```

## Stap 7: De opties wijzigen om verwijderde tekst op te nemen

 Als we verwijderde tekst in het uitvoerresultaat willen opnemen, kunnen we de opties wijzigen zodat verwijderde tekst niet wordt genegeerd. Hiervoor stellen we de`IgnoreDeleted`eigendom aan`false`:

```csharp
options. IgnoreDeleted = false;
```

## Stap 8: Het gewijzigde document met verwijderde tekst uitvoeren

Nadat we de opties hebben gewijzigd, kunnen we het zoeken en vervangen opnieuw uitvoeren om het resultaat te krijgen, inclusief de verwijderde tekst:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Voorbeeldbroncode voor het negeren van tekst binnen het verwijderen van revisies met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om het gebruik van de functie "Tekst binnen verwijderen revisies negeren" te demonstreren met Aspose.Words voor .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Voeg niet-herziene tekst in.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Verwijder de eerste alinea met trackingrevisies.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u de functie 'Tekst negeren binnen verwijderingsrevisies' kunt gebruiken in Aspose.Words voor .NET. Deze functie is handig voor het negeren van tekst in verwijderingsrevisies bij het manipuleren van documenten. We volgden een stapsgewijze handleiding om een document te maken, tekst in te voegen, een alinea te verwijderen met revisietracking, de functie 'Tekst negeren binnen revisies verwijderen' toe te passen en zoek- en vervangbewerkingen uit te voeren.

### Veelgestelde vragen

#### Vraag: Wat is de functie "Tekst in verwijderrevisies negeren" in Aspose.Words voor .NET?

A: Met de functie "Tekst binnen verwijderrevisies negeren" in Aspose.Words voor .NET kunt u opgeven of tekst in verwijderrevisies moet worden genegeerd tijdens bepaalde bewerkingen, zoals het zoeken en vervangen van tekst. Wanneer deze functie is ingeschakeld, wordt tijdens bewerkingen geen rekening gehouden met verwijderde tekst in revisies.

#### Vraag: Wat is Aspose.Words voor .NET?

A: Aspose.Words voor .NET is een krachtige bibliotheek voor het maken, bewerken en converteren van Word-documenten naar .NET-toepassingen. Het biedt veel geavanceerde functies voor tekstverwerking met documenten, inclusief revisiebeheer.

#### Vraag: Hoe maak ik een nieuw document in Aspose.Words voor .NET?

 A: Voordat u tekst in een document gaat manipuleren, moet u een nieuw document maken met Aspose.Words voor .NET. Dit kan gedaan worden door het instantiëren van een`Document` voorwerp. Hier is een voorbeeldcode om een nieuw document te maken:

```csharp
Document doc = new Document();
```

#### Vraag: Hoe kan ik onbewerkte tekst in een document invoegen met Aspose.Words voor .NET?

 A: Zodra u een document heeft, kunt u niet-beoordeelde tekst invoegen met behulp van a`DocumentBuilder` voorwerp. Als u bijvoorbeeld de tekst "Verwijderde tekst" wilt invoegen, kunt u de`Writeln` En`Write` methoden:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### Vraag: Hoe verwijder ik een alinea met revisietracking in Aspose.Words voor .NET?

A: Ter illustratie van het gebruik van de functie "Tekst negeren binnen revisies verwijderen" verwijderen we een alinea uit het document met behulp van het bijhouden van revisies. Hierdoor kunnen we zien hoe deze functie daaropvolgende bewerkingen beïnvloedt.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### Vraag: Hoe kan ik de functie "Tekst negeren binnen verwijderen revisies" inschakelen in Aspose.Words voor .NET?

 A: Nu we ons document hebben voorbereid door een alinea te verwijderen, kunnen we de functie "Tekst negeren binnen revisies verwijderen" inschakelen met behulp van een`FindReplaceOptions` voorwerp. Wij zullen de`IgnoreDeleted`eigendom aan`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### Vraag: Hoe kan ik zoeken en vervangen met reguliere expressies in Aspose.Words voor .NET?

A: Om zoek- en vervangbewerkingen op de tekst van het document uit te voeren, zullen we reguliere expressies gebruiken. In ons voorbeeld zoeken we naar alle exemplaren van de letter "e" en vervangen we deze door een asterisk "* ". We zullen de .NET gebruiken`Regex` klasse hiervoor:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Vraag: Hoe kan ik de gewijzigde documentinhoud bekijken in Aspose.Words voor .NET?

A: Na het toepassen van zoeken en vervangen kunnen we de gewijzigde inhoud van het document weergeven met behulp van de`GetText` methode:

```csharp
Console.WriteLine(doc.GetText());
```

#### Vraag: Hoe kan ik verwijderde tekst opnemen in het uitvoerresultaat in Aspose.Words voor .NET?

 A: Als we verwijderde tekst in het uitvoerresultaat willen opnemen, kunnen we de opties wijzigen zodat de verwijderde tekst niet wordt genegeerd. Hiervoor stellen we de`IgnoreDeleted`eigendom aan`false`:

```csharp
options. IgnoreDeleted = false;
```

#### Vraag: Hoe kan ik een bewerkt document met verwijderde tekst weergeven in Aspose.Words voor .NET?

A: Nadat we de opties hebben gewijzigd, kunnen we opnieuw zoeken en vervangen om het resultaat te krijgen, inclusief de verwijderde tekst:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
