---
title: Woorden van talen afbreken
linktitle: Woorden van talen afbreken
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u woorden in verschillende talen in Word-documenten kunt afbreken met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-hyphenation/hyphenate-words-of-languages/
---

In deze stapsgewijze zelfstudie laten we u zien hoe u woorden in verschillende talen in Word-documenten kunt afbreken met behulp van Aspose.Words voor .NET. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze in uw eigen projecten kunt implementeren.

Zorg er om te beginnen voor dat Aspose.Words voor .NET is geïnstalleerd en geconfigureerd in uw ontwikkelomgeving. Download en installeer de bibliotheek vanaf de officiële site als u dat nog niet heeft gedaan.

## Stap 1: Het documentobject initialiseren

 Initialiseer eerst de`Document` object door het pad op te geven naar uw brondocument dat tekst in verschillende talen bevat:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Stap 2: Afbrekingswoordenboeken opslaan

Sla vervolgens de woordafbrekingswoordenboeken op voor de verschillende talen die u wilt verwerken. In dit voorbeeld registreren we woordenboeken voor Amerikaans Engels en Zwitserduits:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Zorg ervoor dat u de juiste woordenboekbestanden in uw gegevensmap heeft.

## Stap 3: Woorden verwerken door woordafbreking

Nu kunt u afbreekfuncties gebruiken om woorden in verschillende talen te verwerken. Je kunt verschillende methoden gebruiken`Document` of`DocumentBuilder` afhankelijk van uw specifieke behoeften.

```csharp
// Voorbeeld: gebruik van de methode Afbreken van DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Stap 4: Sla het document op

Sla ten slotte het gewijzigde document op:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Dus ! U hebt met succes woorden verwerkt door ze in verschillende talen in een Word-document af te breken met Aspose.Words voor .NET.

### Voorbeeldbroncode voor woordafbreking met Aspose.Words voor .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

doc.Save(dataDir + "TreatmentByCesure.pdf");
```

U kunt deze code gerust in uw eigen projecten gebruiken en aanpassen aan uw specifieke behoeften.

### Veelgestelde vragen

#### Vraag: Hoe kan ik een woord in een specifieke taal syllabiseren met Aspose.Words?

 A: Om een woord in een specifieke taal te syllabiseren met Aspose.Words, kunt u de`Hyphenation` klasse en de`Hyphenate()` methode. Maak een exemplaar van de`Hyphenation` klasse die de gewenste taal specificeert en roep vervolgens de`Hyphenate()` methode waarbij het woord als argument wordt doorgegeven om te syllabiseren. Dit geeft je de lettergrepen van het woord in de opgegeven taal.

#### Vraag: Welke taalcodes moet ik gebruiken om de syllabisatietaal in Aspose.Words te specificeren?

A: Om de syllabisatietaal in Aspose.Words te specificeren, moet u de juiste taalcodes gebruiken. U kunt bijvoorbeeld "en" gebruiken voor Engels, "fr" voor Frans, "es" voor Spaans, "de" voor Duits, enz. Zie de Aspose.Words-documentatie voor een volledige lijst met ondersteunde taalcodes.

#### Vraag: Werkt syllabisatie voor alle talen in Aspose.Words?

A: Syllabisatie in Aspose.Words is afhankelijk van taalspecifieke syllabisatieregels. Hoewel Aspose.Words een breed scala aan talen ondersteunt, worden sommige talen mogelijk niet ondersteund of is syllabisering mogelijk niet beschikbaar voor deze talen. Bekijk de Aspose.Words-documentatie om erachter te komen welke talen worden ondersteund voor syllabisering.