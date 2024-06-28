---
title: Metakarakters in zoekpatroon
linktitle: Metakarakters in zoekpatroon
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u metatekens in het zoekpatroon kunt gebruiken met Aspose.Words voor .NET om Word-documenten te manipuleren.
type: docs
weight: 10
url: /nl/net/find-and-replace-text/meta-characters-in-search-pattern/
---
In dit artikel zullen we de bovenstaande C#-broncode onderzoeken om te begrijpen hoe u de functie Metatekens in zoekpatroon kunt gebruiken in de Aspose.Words voor .NET-bibliotheek. Met deze functie kunt u speciale metatekens gebruiken om geavanceerde zoekopdrachten en vervangingen in Word-documenten uit te voeren.

## Vereisten

- Basiskennis van de C#-taal.
- .NET-ontwikkelomgeving met Aspose.Words-bibliotheek geïnstalleerd.

## Stap 1: Een nieuw document maken

 Voordat we metatekens in het zoekpatroon gaan gebruiken, moeten we een nieuw document maken met Aspose.Words voor .NET. Dit kan gedaan worden door het instantiëren van een`Document` voorwerp:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Stap 2: Voeg tekst in het document in

 Zodra we een document hebben, kunnen we tekst invoegen met behulp van a`DocumentBuilder` voorwerp. In ons voorbeeld gebruiken we de`Writeln` En`Write` methoden om twee regels tekst in te voegen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## Stap 3: Zoek en vervang tekst door metatekens

 Nu zullen we gebruik maken van de`Range.Replace` functie om tekst te zoeken en te vervangen met behulp van een zoekpatroon dat speciale metatekens bevat. In ons voorbeeld vervangen we de zinsnede "Dit is regel 1&pDit is regel 2" door "Deze regel is vervangen" met behulp van de`&p` metateken om een alinea-einde weer te geven:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Stap 4: Een pagina-einde in het document invoegen

 Om het gebruik van een ander metateken te illustreren, voegen we een pagina-einde in het document in met behulp van de`InsertBreak` methode met de`BreakType.PageBreak` parameters. We verplaatsen eerst de cursor van de`DocumentBuilder` aan het einde van het document, waarna we het pagina-einde en een nieuwe regel tekst invoegen:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## Stap 5: Zoek en vervang door een ander metateken

 Nu zullen we nog een keer zoeken en vervangen met behulp van de`&m` metateken om een pagina-einde weer te geven. We vervangen de zinsnede "Dit is regel 1&mDit is regel 2" door "Het pagina-einde is vervangen door nieuwe tekst." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Stap 6: Het bewerkte document opslaan

Ten slotte slaan we het gewijzigde document op in een opgegeven map met behulp van de`Save` methode:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Voorbeeldbroncode voor metatekens in zoekpatroon met Aspose.Words voor .NET

Hier is de volledige voorbeeldbroncode om het gebruik van metatekens in het zoekpatroon met Aspose.Words voor .NET te demonstreren:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Conclusie

In dit artikel hebben we de C#-broncode onderzocht om te begrijpen hoe u metatekens kunt gebruiken in het zoekpatroon van Aspose.Words voor .NET. We volgden een stapsgewijze handleiding om een document te maken, tekst in te voegen, zoeken en vervangen uit te voeren met speciale metatekens, pagina-einden in te voegen en het bewerkte document op te slaan.

### Veelgestelde vragen

#### Vraag: Wat is de functie Metatekens in zoekpatroon in Aspose.Words voor .NET?

A: Met de functie Metatekens in zoekpatroon in Aspose.Words voor .NET kunt u speciale metatekens gebruiken om geavanceerde zoekopdrachten en vervangingen in Word-documenten uit te voeren. Met deze metatekens kunt u alinea-einden, sectie-einden, pagina-einden en andere speciale elementen in uw zoekpatroon weergeven.

#### Vraag: Hoe maak ik een nieuw document in Aspose.Words voor .NET?

 A: Voordat u metatekens in de zoeksjabloon gebruikt, moet u een nieuw document maken met Aspose.Words voor .NET. Dit kan gedaan worden door het instantiëren van een`Document` voorwerp. Hier is een voorbeeldcode om een nieuw document te maken:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Vraag: Hoe kan ik tekst in een document invoegen met Aspose.Words voor .NET?

 A: Zodra u een document heeft, kunt u tekst invoegen met behulp van a`DocumentBuilder` voorwerp. In ons voorbeeld gebruiken we de`Writeln` En`Write` methoden om twee regels tekst in te voegen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### Vraag: Hoe kan ik tekst zoeken en vervangen door metatekens in een document met Aspose.Words voor .NET?

 A: Om tekst te zoeken en te vervangen door metatekens, kunt u de`Range.Replace` methode. In ons voorbeeld vervangen we de zinsnede "Dit is regel 1&pDit is regel 2" door "Deze regel is vervangen" met behulp van de`&p` metateken om een alinea-einde weer te geven:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### Vraag: Hoe kan ik een pagina-einde in een document invoegen met Aspose.Words voor .NET?

A: Om het gebruik van een ander metateken te illustreren, voegen we een pagina-einde in het document in met behulp van de`InsertBreak` methode met de`BreakType.PageBreak` parameters. We verplaatsen eerst de cursor van de`DocumentBuilder` aan het einde van het document, waarna we het pagina-einde en een nieuwe regel tekst invoegen:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### Vraag: Hoe kan ik zoeken en vervangen door een ander metateken in een document met Aspose.Words voor .NET?

 A: We zullen nu opnieuw zoeken en vervangen met behulp van de`&m` metateken om een pagina-einde weer te geven. We vervangen de zinsnede "Dit is regel 1&mDit is regel 2" door "Het pagina-einde is vervangen door nieuwe tekst." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### Vraag: Hoe kan ik een bewerkt document opslaan in Aspose.Words voor .NET?

 A: Nadat u wijzigingen in het document heeft aangebracht, kunt u het in een opgegeven map opslaan met behulp van de`Save` methode:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```