---
title: Horizontale regel
linktitle: Horizontale regel
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een horizontale regel invoegt met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/horizontal-rule/
---

In dit voorbeeld laten we u zien hoe u de horizontale regelfunctie gebruikt met Aspose.Words voor .NET. Horizontale regels worden gebruikt om secties van een document visueel te scheiden.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Een horizontale regel invoegen

 We kunnen een horizontale regel invoegen met behulp van de`InsertHorizontalRule` methode van de documentgenerator.

```csharp
builder. InsertHorizontalRule();
```

## Voorbeeldbroncode voor horizontale regel met Aspose.Words voor .NET

```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

// Horizontale regel invoegen.
builder.InsertHorizontalRule();
```

Gefeliciteerd! U hebt nu geleerd hoe u de horizontale regelfunctie kunt gebruiken met Aspose.Words voor .NET.


### Veelgestelde vragen

#### Vraag: Hoe maak ik een horizontale liniaal in Markdown?

A: Om een horizontale liniaal in Markdown te maken, kunt u een van de volgende symbolen op een lege regel gebruiken: drie sterretjes (\***), drie streepjes (\---), of drie onderstrepingstekens (\___).

#### Vraag: Kan ik het uiterlijk van een horizontale liniaal in Markdown aanpassen?

A: In standaard Markdown is er geen manier om het uiterlijk van horizontale linialen aan te passen. Sommige geavanceerde Markdown-editors en extensies bieden echter extra aanpassingsfuncties.

#### Vraag: Worden horizontale linialen ondersteund door alle Markdown-editors?

A: Ja, de meeste populaire Markdown-editors ondersteunen horizontale linialen. Het is echter altijd het beste om de documentatie van uw specifieke leverancier te controleren om er zeker van te zijn dat deze wordt ondersteund.

#### Vraag: Welke andere elementen kan ik maken in Markdown?

A: Naast horizontale linialen kunt u in Markdown ook titels, alinea's, lijsten, koppelingen, afbeeldingen, tabellen en meer maken.