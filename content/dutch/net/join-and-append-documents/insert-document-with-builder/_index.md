---
title: Document invoegen met Builder
linktitle: Document invoegen met Builder
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u twee Word-documenten kunt samenvoegen met Aspose.Words voor .NET. Stapsgewijze handleiding om een document in te voegen met DocumentBuilder en de opmaak te behouden.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/insert-document-with-builder/
---
## Invoering

heeft dus twee Word-documenten en u wilt ze samenvoegen tot één. Je denkt misschien: "Is er een eenvoudige manier om dit programmatisch te doen?" Absoluut! Vandaag ga ik je door het proces leiden van het invoegen van het ene document in het andere met behulp van de Aspose.Words voor .NET-bibliotheek. Deze methode is superhandig, vooral als je met grote documenten te maken hebt of het proces moet automatiseren. Laten we er meteen in duiken!

## Vereisten

Voordat we aan de slag gaan, zorgen we ervoor dat u alles heeft wat u nodig heeft:

1.  Aspose.Words voor .NET: als u dat nog niet heeft gedaan, kunt u het downloaden van[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Zorg ervoor dat Visual Studio of een andere geschikte IDE is geïnstalleerd.
3. Basiskennis van C#: Met een beetje bekendheid met C# kom je al een heel eind.

## Naamruimten importeren

Allereerst moet u de benodigde naamruimten importeren om toegang te krijgen tot de Aspose.Words-bibliotheekfunctionaliteiten. Hier ziet u hoe u het kunt doen:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Nu we onze vereisten op orde hebben, gaan we het proces stap voor stap opsplitsen.

## Stap 1: Uw documentenmap instellen

Voordat we beginnen met coderen, moet u het pad naar uw documentmap instellen. Hier worden uw bron- en bestemmingsdocumenten opgeslagen.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad waar uw documenten zich bevinden. Hierdoor kan het programma uw bestanden gemakkelijk vinden.

## Stap 2: De bron- en doeldocumenten laden

Vervolgens moeten we de documenten laden waarmee we willen werken. In dit voorbeeld hebben we een brondocument en een bestemmingsdocument.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

 Hier gebruiken we de`Document` klasse uit de Aspose.Words-bibliotheek om onze documenten te laden. Zorg ervoor dat de bestandsnamen overeenkomen met die in uw map.

## Stap 3: Een DocumentBuilder-object maken

 De`DocumentBuilder` class is een krachtig hulpmiddel in de Aspose.Words-bibliotheek. Het stelt ons in staat om door het document te navigeren en het te manipuleren.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

 In deze stap hebben we een`DocumentBuilder` object voor ons bestemmingsdocument. Dit zal ons helpen inhoud in het document in te voegen.

## Stap 4: Naar het einde van het document gaan

We moeten de builder-cursor naar het einde van het doeldocument verplaatsen voordat we het brondocument invoegen.

```csharp
builder.MoveToDocumentEnd();
```

Dit zorgt ervoor dat het brondocument aan het einde van het bestemmingsdocument wordt ingevoegd.

## Stap 5: Een pagina-einde invoegen

Om het overzichtelijk te houden, voegen we een pagina-einde toe voordat we het brondocument invoegen. Hierdoor wordt de inhoud van het brondocument op een nieuwe pagina gestart.

```csharp
builder.InsertBreak(BreakType.PageBreak);
```

Een pagina-einde zorgt ervoor dat de inhoud van het brondocument op een nieuwe pagina begint, waardoor het samengevoegde document er professioneel uitziet.

## Stap 6: Het brondocument invoegen

Nu komt het spannende gedeelte: het invoegen van het brondocument in het doeldocument.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

 De ... gebruiken`InsertDocument` Met deze methode kunnen we het volledige brondocument in het doeldocument invoegen. De`ImportFormatMode.KeepSourceFormatting` zorgt ervoor dat de opmaak van het brondocument behouden blijft.

## Stap 7: Het samengevoegde document opslaan

Laten we ten slotte het samengevoegde document opslaan. Hierdoor worden de bron- en doeldocumenten gecombineerd in één bestand.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Door het document op te slaan, voltooien we het proces van het samenvoegen van de twee documenten. Uw nieuwe document is nu klaar en opgeslagen in de opgegeven map.

## Conclusie

En daar heb je het! U hebt met succes het ene document in het andere ingevoegd met Aspose.Words voor .NET. Deze methode is niet alleen efficiënt, maar behoudt ook de opmaak van beide documenten, waardoor een naadloze samenvoeging wordt gegarandeerd. Of u nu aan een eenmalig project werkt of de documentverwerking moet automatiseren, Aspose.Words voor .NET heeft de oplossing voor u.

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?  
Aspose.Words voor .NET is een krachtige bibliotheek waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, bewerken, converteren en manipuleren.

### Kan ik de opmaak van het brondocument behouden?  
 Ja, door te gebruiken`ImportFormatMode.KeepSourceFormatting`, blijft de opmaak van het brondocument behouden wanneer het in het doeldocument wordt ingevoegd.

### Heb ik een licentie nodig om Aspose.Words voor .NET te gebruiken?  
 Ja, Aspose.Words voor .NET vereist een licentie voor volledige functionaliteit. Je kunt een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor evaluatie.

### Kan ik dit proces automatiseren?  
Absoluut! De beschreven methode kan worden opgenomen in grotere toepassingen om documentverwerkingstaken te automatiseren.

### Waar kan ik meer bronnen en ondersteuning vinden?  
Voor meer informatie kunt u kijken op de[documentatie](https://reference.aspose.com/words/net/) , of bezoek de[Helpforum](https://forum.aspose.com/c/words/8) Voor assistentie.