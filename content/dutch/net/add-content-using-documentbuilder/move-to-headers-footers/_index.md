---
title: Verplaatsen naar kopteksten en voetteksten in Word-document
linktitle: Verplaatsen naar kopteksten en voetteksten in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Aspose.Words voor .NET gebruikt om door kop- en voetteksten in Word-documenten te navigeren en deze aan te passen met deze stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/add-content-using-documentbuilder/move-to-headers-footers/
---
In dit voorbeeld verkennen we de functie Verplaatsen naar kopteksten en voetteksten van Aspose.Words voor .NET. Aspose.Words is een krachtige bibliotheek voor documentmanipulatie waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, wijzigen en converteren. Met de functie Verplaatsen naar kop-/voetteksten kunnen we naar verschillende kop- en voetteksten binnen een document navigeren en er inhoud aan toevoegen.

Laten we de broncode stap voor stap doornemen om te begrijpen hoe u de functie Verplaatsen naar kop-/voetteksten kunt gebruiken met Aspose.Words voor .NET.

## Stap 1: Het document en de documentbuilder initialiseren

Initialiseer eerst de objecten Document en DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Kop- en voetteksten configureren

Geef de kop-/voettekstinstellingen voor het document op. In dit voorbeeld stellen we de kop- en voetteksten anders in voor de eerste pagina en voor oneven/even pagina's:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Stap 3: Kopteksten maken voor verschillende pagina's

Ga naar elk kopteksttype en voeg er inhoud aan toe. In dit voorbeeld maken we kopteksten voor de eerste pagina, even pagina's en alle andere pagina's:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## Stap 4: Pagina's maken in het document
Voeg inhoud aan het document toe om meerdere pagina's te maken. Bijvoorbeeld:

```csharp
// Maak twee pagina's in het document.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## Stap 5: Het document opslaan

Sla het gewijzigde document op een gewenste locatie op:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Zorg ervoor dat u het juiste bestandspad en formaat opgeeft (bijvoorbeeld DOCX).

### Voorbeeldbroncode voor Verplaatsen naar kop-/voetteksten met Aspose.Words voor .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Geef op dat we de kop- en voetteksten verschillend willen hebben voor de eerste, even en oneven pagina's.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Maak de kopteksten.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// Maak twee pagina's in het document.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

## Conclusie

In dit voorbeeld hebben we de functie Verplaatsen naar kop-/voetteksten van Aspose.Words voor .NET onderzocht. We hebben geleerd hoe we naar verschillende kop- en voetteksten binnen een Word-document kunnen navigeren en er inhoud aan kunnen toevoegen met behulp van de DocumentBuilder-klasse. Met deze functie kunnen ontwikkelaars kop- en voetteksten aanpassen voor specifieke pagina's of secties, wat flexibiliteit biedt bij het maken van professionele en gestructureerde documenten. Aspose.Words voor .NET biedt een krachtige set tools voor het programmatisch manipuleren van Word-documenten, waardoor het een essentiële bibliotheek wordt voor documentverwerkingstoepassingen.

### Veelgestelde vragen over het verplaatsen naar kopteksten en voetteksten in een Word-document

#### Vraag: Wat is het doel van de functie Verplaatsen naar kop-/voetteksten in Aspose.Words voor .NET?

A: Met de functie Verplaatsen naar kop-/voetteksten in Aspose.Words voor .NET kunnen ontwikkelaars naar verschillende kop- en voetteksten binnen een Word-document navigeren en er programmatisch inhoud aan toevoegen. Dit is handig wanneer u kop- en voetteksten voor verschillende pagina's of secties in het document moet aanpassen.

#### Vraag: Kan ik verschillende kop- en voetteksten hebben voor verschillende pagina's in het document?

A: Ja, u kunt verschillende kop- en voetteksten opgeven voor de eerste pagina, even pagina's en oneven pagina's met behulp van respectievelijk de eigenschappen PageSetup.DifferentFirstPageHeaderFooter en PageSetup.OddAndEvenPagesHeaderFooter.

#### Vraag: Hoe kan ik inhoud toevoegen aan specifieke kop- en voetteksten?

A: Om inhoud aan specifieke kop- en voetteksten toe te voegen, gebruikt u de MoveToHeaderFooter-methode van de DocumentBuilder-klasse. U kunt naar de headers HeaderFirst, HeaderEven en HeaderPrimary of naar de voetteksten FooterFirst, FooterEven en FooterPrimary gaan, afhankelijk van uw vereisten.

#### Vraag: Kan ik kop- en voetteksten maken voor een specifieke sectie in het document?

A: Ja, u kunt de MoveToSection-methode van de DocumentBuilder-klasse gebruiken om naar een specifieke sectie in het document te gaan en vervolgens binnen die sectie kop- en voetteksten te maken.

#### Vraag: Hoe kan ik het gewijzigde document opslaan in een bestand met Aspose.Words voor .NET?

A: U kunt het gewijzigde document opslaan op een gewenste locatie en in het gewenste formaat met behulp van de Save-methode van de Document-klasse. Zorg ervoor dat u het juiste bestandspad en bestandsformaat opgeeft (bijvoorbeeld DOCX).