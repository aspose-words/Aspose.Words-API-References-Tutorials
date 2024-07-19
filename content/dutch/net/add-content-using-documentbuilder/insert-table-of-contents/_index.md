---
title: Inhoudsopgave invoegen in Word-document
linktitle: Inhoudsopgave invoegen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een inhoudsopgave in Word invoegt met Aspose.Words voor .NET. Volg onze stapsgewijze handleiding voor naadloze documentnavigatie.
type: docs
weight: 10
url: /nl/net/add-content-using-documentbuilder/insert-table-of-contents/
---
## Invoering
In deze zelfstudie leert u hoe u efficiënt een inhoudsopgave (TOC) aan uw Word-documenten kunt toevoegen met Aspose.Words voor .NET. Deze functie is essentieel voor het organiseren en navigeren door lange documenten, het verbeteren van de leesbaarheid en het bieden van een snel overzicht van documentsecties.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

- Basiskennis van C# en .NET-framework.
- Visual Studio is op uw computer geïnstalleerd.
-  Aspose.Words voor .NET-bibliotheek. Als u het nog niet hebt geïnstalleerd, kunt u het downloaden van[hier](https://releases.aspose.com/words/net/).

## Naamruimten importeren

Importeer om te beginnen de benodigde naamruimten in uw C#-project:

```csharp
using Aspose.Words;
using Aspose.Words.Builder;
using Aspose.Words.Fields;
using Aspose.Words.Tables;
```

Laten we het proces in duidelijke stappen opsplitsen:

## Stap 1: Initialiseer Aspose.Words Document en DocumentBuilder

 Initialiseer eerst een nieuwe Aspose.Words`Document` voorwerp en een`DocumentBuilder` werken met:

```csharp
// Initialiseer Document en DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg de inhoudsopgave in

 Voeg nu de inhoudsopgave in met behulp van de`InsertTableOfContents` methode:

```csharp
// Inhoudsopgave invoegen
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Stap 3: Start de documentinhoud op een nieuwe pagina

Om de juiste opmaak te garanderen, begint u de daadwerkelijke documentinhoud op een nieuwe pagina:

```csharp
// Voeg een pagina-einde in
builder.InsertBreak(BreakType.PageBreak);
```

## Stap 4: Structureer uw document met koppen

Organiseer uw documentinhoud met behulp van de juiste kopstijlen:

```csharp
// Kopstijlen instellen
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Stap 5: Werk de inhoudsopgave bij en vul deze in

Werk de inhoudsopgave bij om de documentstructuur weer te geven:

```csharp
// Werk de velden met de inhoudsopgave bij
doc.UpdateFields();
```

## Stap 6: Sla het document op

Sla ten slotte uw document op in een opgegeven map:

```csharp
// Bewaar het document
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
doc.Save(dataDir + "InsertTableOfContentsUsingAsposeWords.docx");
```

## Conclusie

Het toevoegen van een inhoudsopgave met Aspose.Words voor .NET is eenvoudig en verbetert de bruikbaarheid van uw documenten aanzienlijk. Door deze stappen te volgen, kunt u complexe documenten efficiënt organiseren en er doorheen navigeren.

## Veelgestelde vragen

### Kan ik het uiterlijk van de inhoudsopgave aanpassen?
Ja, u kunt het uiterlijk en het gedrag van de inhoudsopgave aanpassen met Aspose.Words voor .NET API's.

### Ondersteunt Aspose.Words het automatisch bijwerken van velden?
Ja, met Aspose.Words kunt u velden zoals de inhoudsopgave dynamisch bijwerken op basis van documentwijzigingen.

### Kan ik meerdere inhoudsopgaven in één document genereren?
Aspose.Words ondersteunt het genereren van meerdere inhoudsopgaven met verschillende instellingen binnen één document.

### Is Aspose.Words compatibel met verschillende versies van Microsoft Word?
Ja, Aspose.Words garandeert compatibiliteit met verschillende versies van Microsoft Word-formaten.

### Waar kan ik meer hulp en ondersteuning vinden voor Aspose.Words?
 Voor meer hulp kunt u terecht op de[Aspose.Words-forum](https://forum.aspose.com/c/words/8) of bekijk de[officiële documentatie](https://reference.aspose.com/words/net/).