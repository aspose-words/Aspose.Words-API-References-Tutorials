---
title: Specificeer de landinstelling op veldniveau
linktitle: Specificeer de landinstelling op veldniveau
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u lokalisatie op veldniveau in Word-documenten kunt opgeven met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/specify-locale-at-field-level/
---

Hier is een stapsgewijze handleiding om de volgende C#-broncode uit te leggen waarmee lokalisatie op veldniveau kan worden opgegeven met behulp van de Aspose.Words voor .NET-functie. Zorg ervoor dat u de Aspose.Words-bibliotheek in uw project hebt opgenomen voordat u deze code gebruikt.

## Stap 1: Stel het documentmappad in

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Zorg ervoor dat u het juiste pad opgeeft naar uw documentenmap waar het bewerkte document zal worden opgeslagen.

## Stap 2: Maak een documentgenerator

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

 Hier maken we een exemplaar van de`DocumentBuilder` class waarmee we velden aan het document kunnen toevoegen.

## Stap 3: Voeg een datumveld in met een specifieke locatie

```csharp
Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;
```

 We gebruiken de documentgenerator om een veld van type in te voegen`FieldType.FieldDate` in het document. Door het instellen van de`LocaleId`eigendom aan`1049`, specificeren we de Russische lokalisatie voor dit veld.

## Stap 4: Sla het gewijzigde document op

```csharp
builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Ten slotte slaan we het gewijzigde document op de opgegeven locatie op in een opgegeven bestand.

### Voorbeeldbroncode voor het opgeven van lokalisatie op veldniveau met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

DocumentBuilder builder = new DocumentBuilder();

Field field = builder. InsertField(FieldType.FieldDate, true);
field.LocaleId = 1049;

builder.Document.Save(dataDir + "WorkingWithFields.SpecifylocaleAtFieldlevel.docx");
```

Dit was een voorbeeld van de broncode om lokalisatie op veldniveau te specificeren in een document met behulp van Aspose.Words voor .NET. U kunt deze code gebruiken om datumvelden met specifieke locaties in uw Word-documenten in te voegen.

### Veelgestelde vragen

#### Vraag: Hoe kan ik de landinstelling op veldniveau opgeven in Aspose.Words voor .NET?

 A: Om de landinstelling op veldniveau in Aspose.Words voor .NET op te geven, kunt u de`FieldOptions` klasse en zijn`FieldLocale` eigenschap om de gewenste landinstelling in te stellen. U kunt bijvoorbeeld gebruiken`FieldOptions.FieldLocale = new CultureInfo("fr-FR")` om de Franse (Frankrijk) landinstelling op te geven.

#### Vraag: Is het mogelijk om voor elk veld in Aspose.Words voor .NET een andere landinstelling op te geven?

 A: Ja, het is mogelijk om voor elk veld in Aspose.Words voor .NET een andere landinstelling op te geven. U kunt gebruik maken van de`FieldOptions.FieldLocale` eigenschap voordat u een specifiek veld maakt of bijwerkt om er een andere landinstelling aan toe te wijzen.

#### Vraag: Hoe kan ik de momenteel gebruikte landinstelling voor een veld in Aspose.Words voor .NET verkrijgen?

 A: Om de momenteel gebruikte landinstelling voor een veld in Aspose.Words voor .NET te verkrijgen, kunt u de`Field.LocaleId`eigendom. Hierdoor kunt u de landinstellings-ID ophalen die aan het veld is gekoppeld.