---
title: Open Type-functies
linktitle: Open Type-functies
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Open Type-functies in Aspose.Words voor .NET inschakelt en gebruikt
type: docs
weight: 10
url: /nl/net/enable-opentype-features/open-type-features/
---

In deze uitgebreide zelfstudie leert u hoe u Open Type-functies in Aspose.Words voor .NET kunt inschakelen en gebruiken. Wij begeleiden u door het proces en voorzien u van de benodigde C#-codefragmenten. Aan het einde van deze handleiding kunt u werken met Open Type-functies in uw Word-documenten.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Laad het document
Om te beginnen laadt u het document met behulp van de klasse Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Stap 2: Open Type-functies inschakelen
Om Open Type-functies in te schakelen, stelt u de eigenschap TextShaperFactory van de klasse LayoutOptions in op een exemplaar van de gewenste Text Shaper Factory. In dit voorbeeld gebruiken we de HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Stap 3: Sla het document op
Nadat u de Open Type-functies hebt ingeschakeld, slaat u het document op in het gewenste uitvoerformaat, zoals PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Voorbeeldbroncode voor Open Type-functies met Aspose.Words voor .NET
Hier is de volledige broncode voor het gebruik van Open Type-functies in Aspose.Words voor .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u Open Type-functies in Aspose.Words voor .NET kunt inschakelen en gebruiken. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u nu met Open Type-functies in uw Word-documenten werken.

Open Type-functies bieden verbeterde mogelijkheden voor typografie en tekstvormgeving, waardoor u visueel aantrekkelijke en professioneel ogende documenten kunt maken. Experimenteer met verschillende tekstvormerfabrieken en ontdek de mogelijkheden van Open Type-functies in uw projecten.

### Veelgestelde vragen

#### Vraag: Hoe schakel ik OpenType-functies in Aspose.Words voor .NET in?

A: Om OpenType-functies in Aspose.Words voor .NET in te schakelen, moet u de stappen volgen die in de zelfstudie worden vermeld.

#### Vraag: Welke OpenType-functies worden ondersteund in Aspose.Words voor .NET?

A: Aspose.Words voor .NET ondersteunt verschillende OpenType-functies, zoals ligaturen, glyph-variaties, contextuele vervangingen en meer.

#### Vraag: Hoe kan ik controleren of een OpenType-functie wordt ondersteund in een specifiek lettertype?

A: U kunt controleren of een OpenType-functie wordt ondersteund in een specifiek lettertype met behulp van de`Font.OpenTypeFeatures` methode in Aspose.Words voor .NET.

#### Vraag: Welke andere tekstopmaakfuncties ondersteunt Aspose.Words voor .NET?

A: Naast OpenType-functies ondersteunt Aspose.Words voor .NET ook andere tekstopmaakfuncties, zoals het opmaken van alinea's, het maken van tabellen, het toevoegen van afbeeldingen, enz.

#### Vraag: Kan ik OpenType-functies gebruiken in alle versies van Aspose.Words voor .NET?

A: OpenType-functies worden ondersteund in nieuwere versies van Aspose.Words voor .NET. Zorg ervoor dat u een compatibele versie gebruikt om van deze functies te kunnen profiteren.