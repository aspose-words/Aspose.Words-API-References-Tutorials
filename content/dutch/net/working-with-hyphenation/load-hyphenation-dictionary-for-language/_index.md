---
title: Afbreekwoordenboek voor taal laden
linktitle: Afbreekwoordenboek voor taal laden
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een woordafbrekingswoordenboek laadt voor een specifieke taal in Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

In deze stapsgewijze zelfstudie laten we u zien hoe u een woordafbrekingswoordenboek voor een specifieke taal in Aspose.Words voor .NET kunt laden. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze in uw eigen projecten kunt implementeren.

 Zorg er om te beginnen voor dat Aspose.Words voor .NET is geïnstalleerd en geconfigureerd in uw ontwikkelomgeving. Als u dat nog niet heeft gedaan, downloadt en installeert u de bibliotheek van[Aspose.Releases]https://releases.aspose.com/words/net/.

## Stap 1: Het document laden

Laad eerst uw document vanuit de opgegeven map:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Stap 2: Het woordafbrekingswoordenboek laden

Open vervolgens een stream naar het woordafbrekingswoordenboekbestand en sla deze op voor de gewenste taal. In dit voorbeeld laden we een woordenboek voor Zwitsers-Duits (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Zorg ervoor dat u het juiste woordenboekbestand in uw gegevensmap heeft.

## Stap 3: Sla het gewijzigde document op

Sla ten slotte het gewijzigde document op:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Dus ! U hebt met succes een woordafbrekingswoordenboek voor een specifieke taal in Aspose.Words voor .NET geladen.

### Voorbeeldbroncode voor het laden van een woordenboek voor woordafbreking voor een taal die Aspose.Words voor .NET gebruikt

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

U kunt deze code gerust in uw eigen projecten gebruiken en aanpassen aan uw specifieke behoeften.

### Veelgestelde vragen

#### Vraag: Hoe laad ik een syllabisatiewoordenboek voor een specifieke taal in Aspose.Words?

 A: Om een syllabisatiewoordenboek voor een specifieke taal in Aspose.Words te laden, kunt u de`Hyphenation` klasse en de`LoadDictionary()` methode. Maak een exemplaar van de`Hyphenation` klas en bel de`LoadDictionary()` methode die het pad specificeert naar het syllabisatiewoordenboekbestand voor de gewenste taal. Hierdoor wordt het syllabisatiewoordenboek in Aspose.Words geladen.

#### Vraag: Waar kan ik syllabisatiewoordenboekbestanden voor verschillende talen vinden?

A: U kunt syllabisatiewoordenboekbestanden voor verschillende talen vinden op verschillende online bronnen. Deze bestanden zijn meestal in XML- of TEX-formaat. U kunt open source syllabisatiewoordenboeken voor verschillende talen vinden op websites die zijn gewijd aan taalkundige projecten of in broncodeopslagplaatsen.

#### Vraag: Hoe kan ik het geladen syllabische woordenboek toepassen op een document in Aspose.Words?

A: Om het geladen syllabiseringswoordenboek toe te passen op een document in Aspose.Words, moet u de woorden in het document herhalen en de`Hyphenate()` werkwijze van de`Hyphenation` klas om de syllabisatie van de woorden te krijgen. Vervolgens kunt u de syllabische woorden naar wens opmaken, bijvoorbeeld door koppeltekens tussen lettergrepen toe te voegen.

#### Vraag: Welke talen worden ondersteund voor syllabisatie in Aspose.Words?

A: Aspose.Words ondersteunt syllabisatie voor meerdere talen, waaronder Engels, Frans, Spaans, Duits, Italiaans, Nederlands, Russisch, Portugees, Zweeds, Noors, Deens, Fins, Pools, Tsjechisch en nog veel meer. Raadpleeg de Aspose.Words-documentatie voor de volledige lijst met ondersteunde talen voor syllabisatie.