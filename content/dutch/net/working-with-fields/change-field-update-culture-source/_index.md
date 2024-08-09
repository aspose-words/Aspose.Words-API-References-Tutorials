---
title: Wijzig veldupdatecultuurbron
linktitle: Wijzig veldupdatecultuurbron
second_title: Aspose.Words-API voor documentverwerking
description: Leer met deze handleiding hoe u de cultuurbron voor veldupdates in Aspose.Words voor .NET kunt wijzigen. Beheer eenvoudig de datumnotatie op basis van verschillende culturen.
type: docs
weight: 10
url: /nl/net/working-with-fields/change-field-update-culture-source/
---
## Invoering

In deze zelfstudie duiken we in de wereld van Aspose.Words voor .NET en onderzoeken we hoe we de veldupdatecultuurbron kunnen wijzigen. Als u te maken heeft met Word-documenten die datumvelden bevatten en u wilt bepalen hoe deze datums worden opgemaakt op basis van verschillende culturen, dan is deze handleiding iets voor u. Laten we het proces stap voor stap doorlopen, zodat u elk concept begrijpt en effectief in uw projecten kunt toepassen.

## Vereisten

Voordat we ingaan op de code, zorg ervoor dat je het volgende hebt:

-  Aspose.Words voor .NET: Je kunt het downloaden van[hier](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: Elke .NET-compatibele IDE (bijvoorbeeld Visual Studio).
- Basiskennis van C#: Deze tutorial gaat ervan uit dat je een fundamenteel begrip hebt van programmeren in C#.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten voor ons project importeren. Dit zorgt ervoor dat we toegang hebben tot alle vereiste klassen en methoden die door Aspose.Words worden aangeboden.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Laten we het voorbeeld nu in meerdere stappen opsplitsen, zodat u begrijpt hoe u de veldupdatecultuurbron in Aspose.Words voor .NET kunt wijzigen.

## Stap 1: Initialiseer het document

 De eerste stap is het maken van een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder`. Dit vormt de basis voor het bouwen en manipuleren van ons Word-document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Velden met een specifieke landinstelling invoegen

Vervolgens moeten we velden in het document invoegen. Voor dit voorbeeld voegen we twee datumvelden in. We stellen de landinstelling van het lettertype in op Duits (LocaleId = 1031) om aan te tonen hoe de cultuur de datumnotatie beïnvloedt.

```csharp
builder.Font.LocaleId = 1031; // Duits
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

## Stap 3: Stel veldupdatecultuurbron in

 Om de cultuur te beheren die wordt gebruikt bij het bijwerken van de velden, stellen we de`FieldUpdateCultureSource` eigendom van de`FieldOptions`klas. Deze eigenschap bepaalt of de cultuur uit de veldcode of uit het document wordt gehaald.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

## Stap 4: Voer Afdruk samenvoegen uit

We moeten nu een samenvoegbewerking uitvoeren om de velden met daadwerkelijke gegevens te vullen. In dit voorbeeld stellen we het tweede datumveld in (`Date2`) tot 1 januari 2011.

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

## Stap 5: Bewaar het document

Ten slotte slaan we het document op in de opgegeven map. Met deze stap wordt het proces van het wijzigen van de veldupdatecultuurbron voltooid.

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Conclusie

En daar heb je het! U hebt de veldupdatecultuurbron in Aspose.Words voor .NET met succes gewijzigd. Door deze stappen te volgen, kunt u ervoor zorgen dat uw Word-documenten datums en andere veldwaarden weergeven volgens de opgegeven cultuurinstellingen. Dit kan met name handig zijn bij het genereren van documenten voor een internationaal publiek.

## Veelgestelde vragen

###  Wat is het doel van het instellen van de`LocaleId`?
 De`LocaleId` specificeert de cultuurinstellingen voor de tekst, die van invloed zijn op de manier waarop datums en andere landgevoelige gegevens worden opgemaakt.

### Kan ik een andere landinstelling dan Duits gebruiken?
 Ja, u kunt de`LocaleId`naar elke geldige locale-ID. Bijvoorbeeld 1033 voor Engels (Verenigde Staten).

###  Wat gebeurt er als ik de`FieldUpdateCultureSource` property?
Als deze eigenschap niet is ingesteld, worden de standaardcultuurinstellingen van het document gebruikt bij het bijwerken van velden.

### Is het mogelijk om velden bij te werken op basis van de cultuur van het document in plaats van op basis van de veldcode?
 Ja, je kunt het instellen`FieldUpdateCultureSource` naar`FieldUpdateCultureSource.Document` om de cultuurinstellingen van het document te gebruiken.

### Hoe kan ik datums in een ander patroon opmaken?
 U kunt het datumnotatiepatroon wijzigen in het`InsertField` methode door het wijzigen van de`\\@` schakel waarde.