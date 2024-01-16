---
title: Veldnamen voor samenvoegen ophalen
linktitle: Veldnamen voor samenvoegen ophalen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u veldnamen voor samenvoegbewerkingen in uw Word-documenten kunt ophalen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/get-mail-merge-field-names/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van de functie "Get Merge Field Names" van Aspose.Words voor .NET. Zorg ervoor dat u elke stap zorgvuldig volgt om de gewenste resultaten te krijgen.

## Stap 1: Documentmap instellen

In de verstrekte code moet u de directory van uw documenten opgeven. Vervang de waarde "UW DOCUMENTENMAP" door het juiste pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Het document laden

De eerste stap is het laden van het document waar u de samenvoegveldnamen wilt ophalen.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Zorg ervoor dat u "UW DOCUMENTBESTAND" vervangt door de naam van uw eigen bestand.

## Stap 3: Haal de samenvoegveldnamen op

 Wij gebruiken de`GetFieldNames()` methode om een array te verkrijgen die de namen bevat van de samenvoegvelden die in het document aanwezig zijn.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 De`fieldNames` variabele bevat nu de namen van de samenvoegvelden.

### Broncodevoorbeeld voor het ophalen van samenvoegveldnamen met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Samenvoegveldnamen ophalen.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Geef het aantal samenvoegvelden weer.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 In dit voorbeeld hebben we een document geladen en de samenvoegveldnamen opgehaald met behulp van de`GetFieldNames()` methode en gaf het aantal samenvoegvelden weer dat in het document aanwezig was.

Dit concludeert onze handleiding over het gebruik van de functie "Get Merge Field Names" met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag 1: Wat is samenvoegen in Aspose.Words?

Afdruk samenvoegen in Aspose.Words is een proces om gegevens uit een externe bron (bijvoorbeeld Excel-spreadsheet of database) samen te voegen met een Word-sjabloondocument om gepersonaliseerde documenten te creëren. Dit vergemakkelijkt het geautomatiseerd genereren van brieven, rapporten en andere soortgelijke documenten.

#### Vraag 2: Hoe krijg ik de lijst met samenvoegvelden die beschikbaar zijn in een Word-document?

Om de lijst met samenvoegvelden te krijgen die beschikbaar zijn in een Word-document, kunt u deze stappen volgen:

1. Importeer de klassen Document en MailMergeFieldNames uit de naamruimte Aspose.Words.
2. Maak een documentinstantie door uw Word-document te laden.
3. Gebruik de GetMailMergeFieldNames-methode van het Document-object om de lijst met beschikbare samenvoegvelden op te halen.

Hier is een voorbeeldcode om het proces te illustreren:

```csharp
// Importeer de benodigde naamruimten
using Aspose.Words;
using Aspose.Words.MailMerging;

// Laad het bestaande document
Document document = new Document("FilePath");

// Lijst met samenvoegvelden ophalen
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Blader door de beschikbare samenvoegvelden
foreach (string fieldName in fieldNames)
{
     // Doe iets met de veldnaam
     Console.WriteLine(fieldName);
}
```
### Veelgestelde vragen

#### Vraag: Wat is samenvoegen in Aspose.Words?

A: Afdruk samenvoegen in Aspose.Words is een proces om gegevens uit een externe bron (bijvoorbeeld een Excel-spreadsheet of database) samen te voegen met een Word-sjabloondocument om gepersonaliseerde documenten te creëren. Dit vergemakkelijkt het geautomatiseerd genereren van brieven, rapporten en andere soortgelijke documenten.

#### Vraag: Hoe krijg ik de lijst met samenvoegvelden die beschikbaar zijn in een Word-document?

A: Om de lijst met samenvoegvelden te krijgen die beschikbaar zijn in een Word-document, kunt u deze stappen volgen:

1. Importeer de klassen Document en MailMergeFieldNames uit de naamruimte Aspose.Words.
2. Maak een documentinstantie door uw Word-document te laden.
3. Gebruik de GetMailMergeFieldNames-methode van het Document-object om de lijst met beschikbare samenvoegvelden op te halen.

#### Vraag: Kan ik samenvoegvelden ophalen uit een externe gegevensbron, zoals een Excel-spreadsheet?

A: Ja, u kunt de samenvoegvelden ophalen uit een externe gegevensbron, zoals een Excel-spreadsheet. Hiervoor kunt u de gegevensbindingsfuncties van Aspose.Words gebruiken om een verbinding tot stand te brengen met de gegevensbron en de namen van de beschikbare velden op te halen.

#### Vraag: Is het mogelijk om samenvoegvelden te filteren op basis van bepaalde criteria?

A: Ja, het is mogelijk om samenvoegvelden te filteren op basis van bepaalde criteria. U kunt reguliere expressies of specifieke voorwaarden gebruiken om samenvoegvelden te filteren, zodat u alleen de velden krijgt die aan uw specifieke criteria voldoen.

#### Vraag: Hoe kan ik samenvoegvelden in Aspose.Words manipuleren?

A: Om mail merge-velden in Aspose.Words te manipuleren, kunt u de methoden en eigenschappen gebruiken die door de Document- en MailMergeField-objecten worden geleverd. U kunt samenvoegvelden toevoegen, verwijderen of bijwerken, en waarden die aan velden zijn gekoppeld, ophalen en bewerken.