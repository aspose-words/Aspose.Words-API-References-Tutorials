---
title: Ga naar sectie in Word-document
linktitle: Ga naar sectie in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het gebruik van Verplaatsen naar sectie in de Word-documentfunctie van Aspose.Words voor .NET om secties en alinea's in Word-documenten te manipuleren.
type: docs
weight: 10
url: /nl/net/add-content-using-documentbuilder/move-to-section/
---
In dit voorbeeld laten we u stap voor stap zien hoe u de functie Verplaatsen naar sectie in Word-documenten van Aspose.Words voor .NET kunt gebruiken met behulp van de meegeleverde C#-broncode. Met deze functie kunt u door verschillende secties in een Word-document navigeren en deze manipuleren. Volg onderstaande stappen om deze functionaliteit in uw applicatie te integreren.

## Stap 1: Maak een nieuw document en voeg een sectie toe

Eerst moeten we een nieuw document maken en er een sectie aan toevoegen. Gebruik de volgende code om deze stap uit te voeren:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Met deze code wordt een nieuw leeg document gemaakt en wordt een sectie aan dit document toegevoegd.

## Stap 2: Verplaats de DocumentBuilder naar de tweede sectie en voeg tekst toe

Vervolgens moeten we de DocumentBuilder naar de tweede sectie van het document verplaatsen en daar wat tekst toevoegen. Gebruik de volgende code om deze stap uit te voeren:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Deze code maakt een DocumentBuilder van het bestaande document en verplaatst vervolgens de cursor van de DocumentBuilder naar de tweede sectie van het document. Ten slotte wordt de opgegeven tekst aan deze sectie toegevoegd.

## Stap 3: Laad een document met bestaande alinea's

Als u met een bestaand document met alinea's wilt werken, kunt u dit document laden met de volgende code:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Deze code laadt het opgegeven document (vervang "MyDir +"Paragraphs.docx"" met het daadwerkelijke pad naar uw document) en geeft toegang tot de verzameling paragrafen uit het eerste gedeelte van het document. De lijn`Assert.AreEqual(22, paragraphs.Count);` controleert of het document 22 paragrafen bevat.

## Stap 4: maak een DocumentBuilder voor een document

U kunt de DocumentBuilder-cursor naar een specifieke alinea maken met behulp van positionele indices.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## Stap 5: Verplaats de cursor naar een specifieke paragraaf


U kunt de DocumentBuilder-cursor naar een specifieke alinea verplaatsen met behulp van positionele indices. Hier leest u hoe u het moet doen:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Deze code verplaatst de cursor van DocumentBuilder naar de derde paragraaf van de tweede sectie (paragraaf op index 2) en naar positie 10. Vervolgens wordt een nieuwe paragraaf met wat tekst toegevoegd en wordt gecontroleerd of de cursor goed op deze nieuwe paragraaf staat.

### Voorbeeldbroncode voor Move To Move To Section met Aspose.Words voor .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// Verplaats een DocumentBuilder naar de tweede sectie en voeg tekst toe.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Maak een document met alinea's.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

// Wanneer we een DocumentBuilder voor een document maken, staat de cursor standaard helemaal aan het begin van het document.
// en alle inhoud die door DocumentBuilder wordt toegevoegd, wordt gewoon aan het document toegevoegd.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

// kunt de cursor naar elke positie in een alinea verplaatsen.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Dat is alles ! U hebt nu begrepen hoe u de functionaliteit voor verplaatsen naar sectie van Aspose.Words voor .NET kunt gebruiken met behulp van de meegeleverde broncode. U kunt deze functionaliteit nu in uw eigen applicatie integreren en secties en paragrafen van uw Word-documenten dynamisch manipuleren.

## Conclusie

In dit voorbeeld hebben we de functie Verplaatsen naar sectie van Aspose.Words voor .NET onderzocht. We hebben geleerd hoe we een nieuw document kunnen maken, er secties aan kunnen toevoegen en de klasse DocumentBuilder kunnen gebruiken om naar specifieke secties en alinea's in een Word-document te navigeren. Deze functie biedt ontwikkelaars krachtige tools om de inhoud en structuur van Word-documenten programmatisch te manipuleren met behulp van Aspose.Words voor .NET.

### Veelgestelde vragen over het verplaatsen naar een sectie in een Word-document

#### Vraag: Wat is het doel van de functie Verplaatsen naar sectie in Aspose.Words voor .NET?

A: Met de functie Verplaatsen naar sectie in Aspose.Words voor .NET kunnen ontwikkelaars programmatisch naar verschillende secties binnen een Word-document navigeren en deze manipuleren. Het biedt de mogelijkheid om inhoud in specifieke secties van het document in te voegen, te wijzigen of te verwijderen.

#### Vraag: Hoe verplaats ik de DocumentBuilder naar een specifieke sectie in een Word-document?

A: Om DocumentBuilder naar een specifieke sectie in een Word-document te verplaatsen, kunt u de MoveToSection-methode van de DocumentBuilder-klasse gebruiken. Deze methode neemt de index van de doelsectie als parameter en plaatst de cursor aan het begin van die sectie.

#### Vraag: Kan ik inhoud toevoegen of wijzigen nadat ik naar een specifieke sectie ben gegaan met behulp van de functie Verplaatsen naar sectie?

A: Ja, zodra DocumentBuilder met MoveToSection in de gewenste sectie is geplaatst, kunt u verschillende methoden van de klasse DocumentBuilder gebruiken, zoals Writeln, Write of InsertHtml, om de inhoud van die sectie toe te voegen of te wijzigen.

#### Vraag: Hoe kan ik met bestaande alinea's in een document werken met behulp van de functie Verplaatsen naar sectie?

A: U kunt een bestaand document met alinea's laden met behulp van de documentconstructor en vervolgens toegang krijgen tot de verzameling alinea's uit de gewenste sectie met behulp van de eigenschap FirstSection.Body.Paragraphs.

#### Vraag: Kan ik de DocumentBuilder-cursor naar een specifieke alinea binnen een sectie verplaatsen met behulp van de functie Verplaatsen naar sectie?

A: Ja, u kunt de DocumentBuilder-cursor naar een specifieke alinea binnen een sectie verplaatsen met behulp van de MoveToParagraph-methode. Deze methode neemt de indices van de doelparagraaf en de tekenpositie (offset) binnen de alinea als parameters.