---
title: Veldcode
linktitle: Veldcode
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om veldcode en veldresultaten in uw Word-documenten te krijgen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/field-code/
---

Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van de functie "Get Field Code" van Aspose.Words voor .NET. Zorg ervoor dat u elke stap zorgvuldig volgt om de gewenste resultaten te krijgen.

## Stap 1: Documentmap instellen

In de verstrekte code moet u de directory van uw documenten opgeven. Vervang de waarde "UW DOCUMENTENMAP" door het juiste pad naar uw documentenmap.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Het document laden

De eerste stap is het uploaden van het document waar u de veldcodes wilt ophalen.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

Zorg ervoor dat u "Hyperlinks.docx" vervangt door de naam van uw eigen bestand.

## Stap 3: Blader door documentvelden

 Wij gebruiken een`foreach` lus om alle velden in het document te doorlopen.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 Bij elke iteratie van de lus krijgen we de veldcode met behulp van de`GetFieldCode()` methode. Het resultaat van het veld slaan we ook op in een variabele.

### Broncodevoorbeeld voor het ophalen van veldcode met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Loop door documentvelden.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // Doe iets met de veldcode en het resultaat.
}
```

In dit voorbeeld hebben we een document geladen en vervolgens door alle velden in het document gebladerd. Bij elke iteratie kregen we de code en het resultaat van het veld. U kunt uw eigen logica toevoegen om de code- en resultaatvelden indien nodig te verwerken.

Dit concludeert onze handleiding over het gebruik van de functie "Get Field Code" met Aspose.Words voor .NET.

### Veelgestelde vragen

#### Vraag: Hoe kan ik een veld invoegen in een Word-document met Aspose.Words voor .NET?

 A: Om een veld in een Word-document in te voegen met Aspose.Words voor .NET, kunt u de`DocumentBuilder.InsertField` methode die de juiste veldcode specificeert. U kunt bijvoorbeeld gebruiken`builder.InsertField("MERGEFIELD CustomerName")` om een samenvoegveld in het document in te voegen.

#### Vraag: Hoe kan ik velden in een document bijwerken met Aspose.Words voor .NET?

 A: Om documentvelden bij te werken met Aspose.Words voor .NET, kunt u de`Document.UpdateFields`methode. Hiermee worden alle velden in het document bijgewerkt, zoals samenvoegvelden, datumvelden, enz.

#### Vraag: Hoe kan ik de waarde van een specifiek veld in Aspose.Words voor .NET ophalen?

 A: Om de waarde van een specifiek veld in Aspose.Words voor .NET op te halen, kunt u de`Field.GetResult` methode door de index van het veld in het`Document.Range.Fields` verzameling. U kunt bijvoorbeeld gebruiken`string value = document.Range.Fields[0].GetResult()` om de waarde van het eerste veld in het document op te halen.

#### Vraag: Hoe kan ik een veld uit een document verwijderen met Aspose.Words voor .NET?

 A: Om een veld uit een document te verwijderen met Aspose.Words voor .NET, kunt u de`Field.Remove` methode die specificeert`Field` object dat u wilt verwijderen. Hierdoor wordt het veld uit het document verwijderd.