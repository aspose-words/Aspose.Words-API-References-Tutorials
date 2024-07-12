---
title: Wijzig de landinstelling
linktitle: Wijzig de landinstelling
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de landinstelling voor datum- en getalopmaak in Word-documenten kunt wijzigen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/change-locale/
---

In deze zelfstudie begeleiden we u bij het wijzigen van de landinstelling in Word-documenten met Aspose.Words voor .NET. Door de landinstelling te wijzigen, kunt u de opmaak van datums en getallen tijdens samenvoegbewerkingen bepalen. Wij voorzien u van de benodigde C#-broncode en stap-voor-stap instructies om dit te realiseren.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Maak een document en DocumentBuilder
Maak om te beginnen een exemplaar van de klasse Document en een DocumentBuilder-object:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg een veld in
Voeg vervolgens een samenvoegveld in het document in met behulp van de InsertField-methode:

```csharp
builder.InsertField("MERGEFIELD Date");
```

In de bovenstaande code voegen we een samenvoegveld met de naam "Datum" in het document in.

## Stap 3: Wijzig de landinstelling
Als u de landinstelling voor de datum- en getalnotatie wilt wijzigen, kunt u de huidige cultuur van de thread wijzigen. In dit voorbeeld stellen we de landinstelling in op Duits ("de-DE"):

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

In de bovenstaande code slaan we de huidige cultuur op en stellen we vervolgens de cultuur van de huidige thread in op Duits.

## Stap 4: Voer Afdruk samenvoegen uit
Voer een samenvoegbewerking uit en geef de datumwaarde op voor het veld 'Datum':

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

In dit codefragment voeren we de samenvoegbewerking uit en geven we de huidige datum op als waarde voor het veld 'Datum'.

## Stap 5: Herstel de oorspronkelijke landinstelling
Nadat het samenvoegen is voltooid, herstelt u de oorspronkelijke cultuur voor de thread:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

In de bovenstaande code herstellen we de oorspronkelijke cultuur van de thread.

## Stap 6: Bewaar het document
Sla het gewijzigde document op in een bestand met behulp van de Save-methode van de Document-klasse:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Voorbeeldbroncode voor het wijzigen van de landinstelling met Aspose.Words voor .NET
Hier is de volledige broncode voor het wijzigen van de landinstelling in Word-documenten met Aspose.Words voor .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u de landinstelling in Word-documenten kunt wijzigen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u nu de opmaak van datums en getallen tijdens samenvoegbewerkingen beheren. Pas de landinstelling aan uw vereisten aan om een nauwkeurige en consistente opmaak in uw documenten te garanderen.

### Veelgestelde vragen

#### Vraag: Is Aspose.Words compatibel met verschillende versies van Microsoft Word?

A: Ja, Aspose.Words is compatibel met verschillende versies van Microsoft Word, waaronder Word 2003, Word 2007, Word 2010, Word 2013, Word 2016 en Word 2019.

#### Vraag: Ondersteunt Aspose.Words complexe veldstructuren?

EEN: Absoluut! Aspose.Words biedt uitgebreide ondersteuning voor complexe veldstructuren, inclusief geneste velden, berekeningen en voorwaardelijke expressies. U kunt deze krachtige API gebruiken om met elk type veldstructuur te werken.

#### Vraag: Ondersteunt Aspose.Words veldupdatebewerkingen?

A: Ja, met Aspose.Words kunt u velden volgens een schema bijwerken. Met behulp van de API kunt u eenvoudig veldwaarden bijwerken, berekeningen vernieuwen en andere veldgerelateerde bewerkingen uitvoeren.

#### Vraag: Is het mogelijk om velden naar platte tekst te converteren met Aspose.Words?

EEN: Zeker! Aspose.Words biedt methoden om velden naar platte tekst te converteren. Dit kan handig zijn als u de inhoud moet extraheren zonder enige opmaak of veldgerelateerde functionaliteit.

#### Vraag: Is het mogelijk om Word-documenten met dynamische velden te genereren met behulp van Aspose.Words?

EEN: Absoluut! Aspose.Words biedt robuuste functionaliteit voor het genereren van Word-documenten met dynamische velden. U kunt sjablonen maken met vooraf gedefinieerde velden en deze dynamisch vullen met gegevens, waardoor u een flexibele en efficiënte oplossing krijgt voor het genereren van documenten.