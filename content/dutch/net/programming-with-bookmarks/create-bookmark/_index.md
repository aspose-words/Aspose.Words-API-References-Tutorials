---
title: Maak een bladwijzer in een Word-document
linktitle: Maak een bladwijzer in een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u bladwijzers in Word-documenten kunt maken met Aspose.Words voor .NET met deze gedetailleerde, stapsgewijze handleiding. Perfect voor documentnavigatie en organisatie.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/create-bookmark/
---
## Invoering

Het maken van bladwijzers in een Word-document kan een grote verandering teweegbrengen, vooral als u moeiteloos door grote documenten wilt navigeren. Vandaag doorlopen we het proces van het maken van bladwijzers met Aspose.Words voor .NET. Deze tutorial neemt je stap voor stap mee, zodat je elk onderdeel van het proces begrijpt. Dus laten we er meteen in duiken!

## Vereisten

Voordat we beginnen, moet u over het volgende beschikken:

1.  Aspose.Words voor .NET-bibliotheek: downloaden en installeren vanaf[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Visual Studio of een andere .NET-ontwikkelomgeving.
3. Basiskennis van C#: inzicht in de basisconcepten van C#-programmeren.

## Naamruimten importeren

Om met Aspose.Words voor .NET te werken, moet u de benodigde naamruimten importeren:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Stap 1: Stel het Document en DocumentBuilder in

Initialiseer het document

Eerst moeten we een nieuw document maken en het`DocumentBuilder`. Dit is het startpunt voor het toevoegen van inhoud en bladwijzers aan uw document.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Uitleg: De`Document` object is je canvas. De`DocumentBuilder` is als uw pen, waarmee u inhoud kunt schrijven en bladwijzers in het document kunt maken.

## Stap 2: Maak de hoofdbladwijzer

Start en beëindig de hoofdbladwijzer

Als u een bladwijzer wilt maken, moet u het begin- en eindpunt opgeven. Hier maken we een bladwijzer met de naam "Mijn bladwijzer".

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");
```

 Uitleg: De`StartBookmark` methode markeert het begin van de bladwijzer, en`Writeln` voegt tekst toe aan de bladwijzer.

## Stap 3: Maak een geneste bladwijzer

Voeg geneste bladwijzer toe in de hoofdbladwijzer

U kunt bladwijzers in andere bladwijzers nesten. Hier voegen we "Geneste bladwijzer" toe aan "Mijn bladwijzer".

```csharp
builder.StartBookmark("Nested Bookmark");
builder.Writeln("Text inside a NestedBookmark.");
builder.EndBookmark("Nested Bookmark");
```

 Uitleg: Het nesten van bladwijzers maakt een meer gestructureerde en hiërarchische organisatie van de inhoud mogelijk. De`EndBookmark` methode sluit de huidige bladwijzer.

## Stap 4: Voeg tekst toe buiten de geneste bladwijzer

Ga door met het toevoegen van inhoud

Na de geneste bladwijzer kunnen we doorgaan met het toevoegen van meer inhoud binnen de hoofdbladwijzer.

```csharp
builder.Writeln("Text after Nested Bookmark.");
builder.EndBookmark("My Bookmark");
```

Uitleg: Dit zorgt ervoor dat de hoofdbladwijzer zowel de geneste bladwijzer als aanvullende tekst omvat.

## Stap 5: Configureer de PDF-opslagopties

PDF-opslagopties voor bladwijzers instellen

Wanneer we het document als PDF opslaan, kunnen we opties configureren om bladwijzers op te nemen.

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);
```

 Uitleg: De`PdfSaveOptions` Met class kunt u opgeven hoe het document als PDF moet worden opgeslagen. De`BookmarksOutlineLevels` eigenschap definieert de hiërarchie van de bladwijzers in de PDF.

## Stap 6: Sla het document op

Sla het document op als PDF

Sla ten slotte het document op met de opgegeven opties.

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

 Uitleg: De`Save` methode slaat het document op in het opgegeven formaat en de opgegeven locatie. De PDF bevat nu de bladwijzers die we hebben gemaakt.

## Conclusie

Het maken van bladwijzers in een Word-document met Aspose.Words voor .NET is eenvoudig en enorm handig voor documentnavigatie en -organisatie. Of u nu rapporten genereert, eBooks maakt of grote documenten beheert, bladwijzers maken het leven gemakkelijker. Volg de stappen die in deze zelfstudie worden beschreven en u heeft binnen een mum van tijd een PDF met bladwijzer klaar.

## Veelgestelde vragen

### Kan ik meerdere bladwijzers op verschillende niveaus aanmaken?

Absoluut! U kunt zoveel bladwijzers maken als nodig is en hun hiërarchische niveaus definiëren wanneer u het document als PDF opslaat.

### Hoe werk ik de tekst van een bladwijzer bij?

 U kunt naar de bladwijzer navigeren met behulp van`DocumentBuilder.MoveToBookmark` en vervolgens de tekst bijwerken.

### Is het mogelijk om een bladwijzer te verwijderen?

 Ja, u kunt een bladwijzer verwijderen met behulp van de`Bookmarks.Remove` methode door de naam van de bladwijzer op te geven.

### Kan ik bladwijzers in andere formaten dan PDF maken?

Ja, Aspose.Words ondersteunt bladwijzers in verschillende formaten, waaronder DOCX, HTML en EPUB.

### Hoe kan ik ervoor zorgen dat de bladwijzers correct in de PDF worden weergegeven?

 Zorg ervoor dat u de definieert`BookmarksOutlineLevels` behoorlijk in de`PdfSaveOptions`. Dit zorgt ervoor dat de bladwijzers worden opgenomen in de omtrek van de PDF.