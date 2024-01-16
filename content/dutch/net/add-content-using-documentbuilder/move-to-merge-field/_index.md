---
title: Verplaats naar veld samenvoegen in Word-document
linktitle: Verplaats naar veld samenvoegen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de functie Verplaatsen naar samenvoegveld in Word-documenten van Aspose.Words voor .NET implementeert met behulp van een stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/add-content-using-documentbuilder/move-to-merge-field/
---
In dit voorbeeld verkennen we de functie Verplaatsen naar samenvoegveld in Word-documenten van Aspose.Words voor .NET. Aspose.Words is een krachtige bibliotheek voor documentmanipulatie waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, wijzigen en converteren. Met de functie Verplaatsen naar samenvoegveld kunnen we navigeren om velden binnen een document samen te voegen en er verschillende bewerkingen op uit te voeren.


## De broncode stap voor stap uitleggen

Laten we de broncode stap voor stap doornemen om te begrijpen hoe u de functie Move To Merge Field kunt gebruiken met Aspose.Words voor .NET.

## Stap 1: Het document en de documentbuilder initialiseren

Initialiseer eerst de objecten Document en DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2 Een samenvoegveld invoegen en er tekst achteraan toevoegen

Gebruik de InsertField-methode van de DocumentBuilder-klasse om een samenvoegveld in te voegen en daarna tekst toe te voegen:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Stap 3: De cursor van de bouwer bevindt zich momenteel aan het einde van het document.

```csharp
Assert.Null(builder.CurrentNode);
```
## Stap 4: Verplaats de cursor van de documentbouwer naar het samenvoegveld

Om de documentbuilder-cursor naar het samenvoegveld te verplaatsen, gebruikt u de MoveToField-methode van de DocumentBuilder-klasse:

```csharp
builder.MoveToField(field, true);
```

## Tekst toevoegen onmiddellijk na het samenvoegveld

Zodra de documentbuilder-cursor zich in het samenvoegveld bevindt, kunt u er direct daarna tekst aan toevoegen met behulp van de Write-methode:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Voorbeeldbroncode voor Verplaatsen naar samenvoegveld met Aspose.Words voor .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Voeg een veld in met de DocumentBuilder en voeg er een stuk tekst aan toe.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// De cursor van de bouwer bevindt zich momenteel aan het einde van het document.
Assert.Null(builder.CurrentNode);
// We kunnen de bouwer naar een veld als dit verplaatsen, door de cursor direct na het veld te plaatsen.
builder.MoveToField(field, true);

// Merk op dat de cursor zich op een plaats voorbij het FieldEnd-knooppunt van het veld bevindt, wat betekent dat we ons niet daadwerkelijk in het veld bevinden.
// Als we de DocumentBuilder naar binnen een veld willen verplaatsen,
// we zullen het moeten verplaatsen naar het FieldStart- of FieldSeparator-knooppunt van een veld met behulp van de DocumentBuilder.MoveTo() -methode.
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Conclusie

we hebben de functie Move To Merge Field van Aspose.Words voor .NET onderzocht. We hebben geleerd hoe u kunt navigeren om velden binnen een document samen te voegen met behulp van de klasse DocumentBuilder en er bewerkingen op kunt uitvoeren. Deze functie is handig bij programmatische woordverwerking met samenvoeging

### Veelgestelde vragen over het samenvoegen van velden in een Word-document

#### Vraag: Wat is het doel van de functie Verplaatsen naar samenvoegveld in Aspose.Words voor .NET?

A: Met de functie 'Verplaats naar samenvoegveld' in Aspose.Words voor .NET kunnen ontwikkelaars navigeren om velden binnen een Word-document samen te voegen en er programmatisch verschillende bewerkingen op uit te voeren. Samenvoegvelden zijn speciale tijdelijke aanduidingen die in Word-documenten worden gebruikt voor samenvoegbewerkingen.

#### Vraag: Hoe kan ik een samenvoegveld invoegen in een Word-document met Aspose.Words voor .NET?

A: U kunt de InsertField-methode van de DocumentBuilder-klasse gebruiken om een samenvoegveld in het document in te voegen. Nadat u het samenvoegveld hebt ingevoegd, kunt u inhoud, zoals tekst, voor of na het veld toevoegen met behulp van de Write-methode.

#### Vraag: Hoe verplaats ik de cursor van de documentbouwer naar een specifiek samenvoegveld?

A: Om de documentbuilder-cursor naar een specifiek samenvoegveld te verplaatsen, gebruikt u de MoveToField-methode van de DocumentBuilder-klasse en geeft u het veld door als parameter. Hierdoor wordt de cursor onmiddellijk na het samenvoegveld geplaatst.

#### Vraag: Kan ik tekst toevoegen aan een samenvoegveld met behulp van de functie Verplaatsen naar samenvoegveld?

A: Nee, de functie Verplaatsen naar samenvoegveld plaatst de documentbuilder-cursor onmiddellijk na het samenvoegveld. Als u tekst in het samenvoegveld wilt toevoegen, kunt u de methode DocumentBuilder.MoveTo gebruiken om de cursor naar het knooppunt FieldStart of FieldSeparator van het samenvoegveld te verplaatsen.

#### Vraag: Hoe kan ik samenvoegbewerkingen uitvoeren met Aspose.Words voor .NET?

A: Aspose.Words voor .NET biedt uitgebreide ondersteuning voor samenvoegbewerkingen. U kunt de klasse MailMerge gebruiken om samenvoegbewerkingen uit te voeren met behulp van gegevens uit verschillende bronnen, zoals arrays, gegevenssets of aangepaste gegevensbronnen.