---
title: Bladwijzer maken in Word-document
linktitle: Bladwijzer maken in Word-document
second_title: Aspose.Words API voor documentverwerking
description: Leer hoe u bladwijzers in Word-documenten kunt maken met Aspose.Words voor .NET met deze gedetailleerde, stapsgewijze handleiding. Perfect voor documentnavigatie en -organisatie.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/create-bookmark/
---
## Invoering

Bladwijzers maken in een Word-document kan een game-changer zijn, vooral als u moeiteloos door grote documenten wilt navigeren. Vandaag doorlopen we het proces van het maken van bladwijzers met Aspose.Words voor .NET. Deze tutorial neemt u stap voor stap mee, zodat u elk onderdeel van het proces begrijpt. Dus laten we er meteen induiken!

## Vereisten

Voordat we beginnen, moet u over het volgende beschikken:

1.  Aspose.Words voor .NET-bibliotheek: downloaden en installeren vanaf[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Visual Studio of een andere .NET-ontwikkelomgeving.
3. Basiskennis van C#: inzicht in de basisconcepten van C#-programmeren.

## Naamruimten importeren

Om met Aspose.Words voor .NET te kunnen werken, moet u de benodigde naamruimten importeren:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Stap 1: Het document en de DocumentBuilder instellen

Initialiseer het document

Eerst moeten we een nieuw document maken en het initialiseren`DocumentBuilder`Dit is het startpunt voor het toevoegen van inhoud en bladwijzers aan uw document.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Uitleg: De`Document` object is jouw canvas. Het`DocumentBuilder` is als een pen waarmee u tekst kunt schrijven en bladwijzers in het document kunt maken.

## Stap 2: Maak de hoofdbladwijzer

Start en eindig de hoofdbladwijzer

Om een bladwijzer te maken, moet u het begin- en eindpunt opgeven. Hier maken we een bladwijzer met de naam "Mijn bladwijzer".

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");
```

 Uitleg: De`StartBookmark` methode markeert het begin van de bladwijzer, en`Writeln` voegt tekst toe aan de bladwijzer.

## Stap 3: Een geneste bladwijzer maken

Geneste bladwijzer toevoegen in de hoofdbladwijzer

U kunt bladwijzers nesten in andere bladwijzers. Hier voegen we "Nested Bookmark" toe in "My Bookmark".

```csharp
builder.StartBookmark("Nested Bookmark");
builder.Writeln("Text inside a NestedBookmark.");
builder.EndBookmark("Nested Bookmark");
```

 Uitleg: Het nesten van bladwijzers zorgt voor een meer gestructureerde en hiërarchische organisatie van de inhoud.`EndBookmark` methode sluit de huidige bladwijzer.

## Stap 4: Tekst toevoegen buiten de geneste bladwijzer

Blijf inhoud toevoegen

Na de geneste bladwijzer kunnen we doorgaan met het toevoegen van meer inhoud binnen de hoofdbladwijzer.

```csharp
builder.Writeln("Text after Nested Bookmark.");
builder.EndBookmark("My Bookmark");
```

Uitleg: Hiermee wordt ervoor gezorgd dat de hoofdbladwijzer zowel de geneste bladwijzer als de aanvullende tekst omvat.

## Stap 5: PDF-opslagopties configureren

PDF-opslagopties voor bladwijzers instellen

Wanneer u het document als PDF opslaat, kunt u opties configureren om bladwijzers toe te voegen.

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);
```

 Uitleg: De`PdfSaveOptions` Met de klasse kunt u opgeven hoe het document als PDF moet worden opgeslagen.`BookmarksOutlineLevels` eigenschap definieert de hiërarchie van de bladwijzers in de PDF.

## Stap 6: Sla het document op

Sla het document op als PDF

Sla ten slotte het document op met de opgegeven opties.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

 Uitleg: De`Save` methode slaat het document op in het opgegeven formaat en de opgegeven locatie. De PDF zal nu de bladwijzers bevatten die we hebben gemaakt.

## Conclusie

Bladwijzers maken in een Word-document met Aspose.Words voor .NET is eenvoudig en enorm handig voor documentnavigatie en -organisatie. Of u nu rapporten genereert, e-books maakt of grote documenten beheert, bladwijzers maken het leven gemakkelijker. Volg de stappen in deze tutorial en u hebt in een mum van tijd een PDF met bladwijzers klaar.

## Veelgestelde vragen

### Kan ik meerdere bladwijzers op verschillende niveaus maken?

Absoluut! U kunt zoveel bladwijzers maken als nodig is en hun hiërarchische niveaus definiëren wanneer u het document opslaat als een PDF.

### Hoe kan ik de tekst van een bladwijzer bijwerken?

 U kunt naar de bladwijzer navigeren met`DocumentBuilder.MoveToBookmark` en werk vervolgens de tekst bij.

### Is het mogelijk om een bladwijzer te verwijderen?

 Ja, u kunt een bladwijzer verwijderen met behulp van de`Bookmarks.Remove` methode door de naam van de bladwijzer op te geven.

### Kan ik bladwijzers maken in andere formaten dan PDF?

Ja, Aspose.Words ondersteunt bladwijzers in verschillende formaten, waaronder DOCX, HTML en EPUB.

### Hoe kan ik ervoor zorgen dat de bladwijzers correct in de PDF worden weergegeven?

 Zorg ervoor dat u de`BookmarksOutlineLevels` goed in de`PdfSaveOptions`Hiermee wordt ervoor gezorgd dat de bladwijzers in de PDF-contour worden opgenomen.