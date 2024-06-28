---
title: Velden in alinea converteren
linktitle: Velden in alinea converteren
second_title: Aspose.Words-API voor documentverwerking
description: Converteer IF-velden naar platte tekst in een alinea met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fields/convert-fields-in-paragraph/
---

Hier is een tutorial waarin wordt gedemonstreerd hoe u de functie Velden naar alinea converteren kunt gebruiken met Aspose.Words voor .NET. Deze code converteert alle velden van het IF-type die u in de laatste alinea van een document tegenkomt, naar platte tekst. Volg de onderstaande stappen om deze code te begrijpen en uit te voeren.

Zorg ervoor dat u Aspose.Words voor .NET hebt geïnstalleerd en uw ontwikkelomgeving hebt ingesteld voordat u begint.

## Stap 1: Referenties importeren

Om Aspose.Words in uw project te gebruiken, moet u de nodige referenties toevoegen. Zorg ervoor dat u een verwijzing naar de Aspose.Words-bibliotheek in uw project hebt toegevoegd.

## Stap 2: Het document laden

Voordat u velden kunt converteren, moet u het document laden dat de te converteren velden bevat. Zorg ervoor dat u het juiste pad opgeeft naar de map die het document bevat. Zo uploadt u het document:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Vervang "UW DOCUMENTENMAP" door het daadwerkelijke pad naar uw documentenmap.

## Stap 3: Velden naar tekst converteren

Nu het document is geladen, kunnen we doorgaan met het converteren van de typevelden naar platte tekst. In dit voorbeeld targeten we alleen de velden in de laatste alinea van het document. Hier is de code die deze conversie uitvoert:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Deze code gebruikt een combinatie van LINQ-methoden om velden in de laatste alinea van het document uit te filteren en converteert ze vervolgens naar platte tekst door de`Unlink()` methode.

## Stap 4: Het gewijzigde document opslaan

 Nadat de velden zijn geconverteerd, kunt u het gewijzigde document opslaan. Gebruik de`Save()` methode hiervoor. Hier is een voorbeeld :

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor de back-up opgeeft.

### Broncodevoorbeeld voor het converteren van velden in alinea met Aspose.Words voor .NET

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document.
Document doc = new Document(dataDir + "Linked fields.docx");

// Converteer IF-velden naar platte tekst in de laatste alinea van het document.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Sla het gewijzigde document op.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### Veelgestelde vragen

#### Vraag: Wat is een conversieveld in Aspose.Words?

A: Een conversieveld in Aspose.Words is een type veld dat een waarde of expressie omzet naar een ander formaat of gegevenstype. U kunt een conversieveld bijvoorbeeld gebruiken om een datum naar een specifiek formaat, een getal naar tekst, te converteren of andere typen conversies uit te voeren.

#### Vraag: Hoe voeg ik een conversieveld in een alinea in met Aspose.Words?

A: Om een conversieveld in een alinea in te voegen met Aspose.Words, kunt u deze stappen volgen:

1. Importeer de Document-klasse uit de Aspose.Words-naamruimte.
2. Maak een exemplaar van Document door uw bestaande document te laden.
3. Haal de alinea op waar u het conversieveld wilt invoegen.
4. Gebruik de InsertField-methode om het conversieveld met de juiste syntaxis in te voegen.

#### Vraag: Welke conversieformaten ondersteunt Aspose.Words?

A: Aspose.Words ondersteunt een breed scala aan conversieformaten in velden, waaronder datumformaten, getalformaten, tekstformaten, valutaformaten, percentageformaten en meer. U kunt de Aspose.Words-documentatie raadplegen voor een volledige lijst met beschikbare conversieformaten.

#### Vraag: Hoe kan ik een conversieveld in een Word-document bijwerken met Aspose.Words?

A: Om een conversieveld in een Word-document bij te werken met Aspose.Words, kunt u de UpdateFields-methode gebruiken. Deze methode loopt door het document en werkt alle velden bij, inclusief conversievelden, waarbij waarden opnieuw worden berekend op basis van de huidige gegevens.