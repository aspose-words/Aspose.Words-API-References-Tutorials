---
title: Meeteenheid
linktitle: Meeteenheid
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de maateenheid kunt opgeven bij het converteren van een Word-document naar ODT met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-odtsaveoptions/measure-unit/
---

Wanneer u een Word-document converteert naar de OpenDocument Text-indeling (ODT) in een C#-toepassing, wilt u mogelijk de maateenheid opgeven die wordt gebruikt voor meetbare opmaak en inhoudseigenschappen. Met de Aspose.Words-bibliotheek voor .NET kunt u deze functionaliteit eenvoudig specificeren met behulp van de OdtSaveOptions-opslagopties. In deze stapsgewijze handleiding laten we u zien hoe u Aspose.Words voor .NET C#-broncode kunt gebruiken om een Word-document naar ODT te converteren door de maateenheid op te geven met OdtSaveOptions.

## Inzicht in de Aspose.Words-bibliotheek

Voordat u in de code duikt, is het belangrijk dat u de Aspose.Words-bibliotheek voor .NET begrijpt. Aspose.Words is een krachtige bibliotheek voor het maken, bewerken, converteren en beschermen van Word-documenten op verschillende platforms, waaronder .NET. Het biedt veel functies voor het manipuleren van documenten, zoals het invoegen van tekst, het wijzigen van de opmaak, het toevoegen van secties en nog veel meer.

## Het Word-document laden

De eerste stap is het laden van het Word-document dat u naar ODT wilt converteren. Gebruik de klasse Document om het document uit het bronbestand te laden. Hier is een voorbeeld :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In dit voorbeeld laden we het document "Document.docx" in de documentenmap.

## Back-upopties configureren

De volgende stap is het configureren van de back-upopties voor het converteren naar ODT. Gebruik de klasse OdtSaveOptions en stel de eigenschap MeasureUnit in op de gewenste waarde. Als u bijvoorbeeld inches als maateenheid wilt gebruiken, stelt u MeasureUnit in op OdtSaveMeasureUnit.Inches. Hier leest u hoe u het moet doen:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

We maken een nieuw OdtSaveOptions-object en stellen de eigenschap MeasureUnit in op de gewenste waarde, in ons geval OdtSaveMeasureUnit.Inches om inches als maateenheid te gebruiken.

## Converteer document naar ODT

Nu we de opslagopties hebben geconfigureerd, kunnen we doorgaan met het converteren van het document naar ODT. Gebruik de Save-methode van de Document-klasse om het geconverteerde document in ODT-indeling op te slaan door opslagopties op te geven. Hier is een voorbeeld :

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

In dit voorbeeld slaan we het geconverteerde document op als "WorkingWithOdtSaveOptions.MeasureUnit.odt" met behulp van de opgegeven opslagopties.

### Voorbeeldbroncode voor OdtSaveOptions met "Meeteenheid"-functionaliteit met behulp van Aspose.Words voor .NET



```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het Word-document
Document doc = new Document(dataDir + "Document.docx");

// Configuratie van back-upopties met de functie "Meeteenheid".
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Converteer het document naar ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Conclusie

In deze handleiding hebben we uitgelegd hoe u een Word-document naar ODT kunt converteren door de maateenheid op te geven met behulp van de OdtSaveOptions-opslagopties met de Aspose.Words-bibliotheek voor .NET. Door de meegeleverde stappen te volgen en de meegeleverde C#-broncode te gebruiken, kunt u deze functionaliteit eenvoudig toepassen in uw C#-applicatie. Door de maateenheid op te geven bij het converteren naar ODT, kunt u de opmaak en afmetingen van het resulterende document beheren volgens uw specifieke behoeften.