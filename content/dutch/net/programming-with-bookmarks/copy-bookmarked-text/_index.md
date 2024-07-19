---
title: Kopieer de tekst met bladwijzer naar een Word-document
linktitle: Kopieer de tekst met bladwijzer naar een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Kopieer tekst met bladwijzers moeiteloos tussen Word-documenten met Aspose.Words voor .NET. Leer hoe u dit doet met deze stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/copy-bookmarked-text/
---
## Invoering

Ooit gemerkt dat u specifieke secties van het ene Word-document naar het andere moest kopiëren? Nou, je hebt geluk! In deze zelfstudie laten we u zien hoe u tekst met een bladwijzer van het ene Word-document naar het andere kunt kopiëren met Aspose.Words voor .NET. Of u nu een dynamisch rapport bouwt of het genereren van documenten automatiseert, deze handleiding zal het proces voor u vereenvoudigen.

## Vereisten

Voordat we erin duiken, zorg ervoor dat je het volgende hebt:

-  Aspose.Words voor .NET-bibliotheek: u kunt het downloaden van[hier](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: Visual Studio of een andere .NET-ontwikkelomgeving.
- Basiskennis van C#: Bekendheid met C#-programmeren en .NET-framework.

## Naamruimten importeren

Zorg er om te beginnen voor dat u de benodigde naamruimten in uw project importeert:

```csharp
using Aspose.Words;
using Aspose.Words.Import;
using Aspose.Words.Bookmark;
```

## Stap 1: Laad het brondocument

Allereerst moet u het brondocument laden dat de tekst met bladwijzer bevat die u wilt kopiëren.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

 Hier,`dataDir` is het pad naar uw documentmap, en`Bookmarks.docx` is het brondocument.

## Stap 2: Identificeer de bladwijzer

Identificeer vervolgens de bladwijzer die u uit het brondocument wilt kopiëren.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

 Vervangen`"MyBookmark1"` met de werkelijke naam van uw bladwijzer.

## Stap 3: Maak het bestemmingsdocument

Maak nu een nieuw document waarin de tekst met de bladwijzer wordt gekopieerd.

```csharp
Document dstDoc = new Document();
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Stap 4: Importeer inhoud met bladwijzers

 Om ervoor te zorgen dat de stijlen en opmaak behouden blijven, gebruikt u`NodeImporter` om de inhoud met bladwijzer van het brondocument naar het doeldocument te importeren.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(importer, srcBookmark, dstNode);
```

## Stap 5: Definieer de AppendBookmarkedText-methode

Hier gebeurt de magie. Definieer een methode om het kopiëren van de tekst met bladwijzer af te handelen:

```csharp
private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
{
    Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
    Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

    if (startPara == null || endPara == null)
        throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

    if (startPara.ParentNode != endPara.ParentNode)
        throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");

    Node endNode = endPara.NextSibling;

    for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
    {
        Node newNode = importer.ImportNode(curNode, true);
        dstNode.AppendChild(newNode);
    }
}
```

## Stap 6: Sla het bestemmingsdocument op

Sla ten slotte het doeldocument op om de gekopieerde inhoud te verifiëren.

```csharp
dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## Conclusie

En dat is het! U hebt met succes tekst met een bladwijzer van het ene Word-document naar het andere gekopieerd met Aspose.Words voor .NET. Deze methode is krachtig voor het automatiseren van documentmanipulatietaken, waardoor uw workflow efficiënter en gestroomlijnder wordt.

## Veelgestelde vragen

### Kan ik meerdere bladwijzers tegelijk kopiëren?
Ja, u kunt meerdere bladwijzers doorlopen en dezelfde methode gebruiken om ze allemaal te kopiëren.

### Wat gebeurt er als de bladwijzer niet wordt gevonden?
 De`Range.Bookmarks` eigendom zal terugkeren`null`Zorg er dus voor dat u deze zaak afhandelt om uitzonderingen te voorkomen.

### Kan ik de opmaak van de originele bladwijzer behouden?
 Absoluut! Gebruik makend van`ImportFormatMode.KeepSourceFormatting` zorgt ervoor dat de originele opmaak behouden blijft.

### Is er een limiet aan de grootte van de tekst in de bladwijzer?
Er is geen specifieke limiet, maar de prestaties kunnen variëren bij extreem grote documenten.

### Kan ik tekst kopiëren tussen verschillende Word-documentformaten?
Ja, Aspose.Words ondersteunt verschillende Word-formaten en de methode werkt in deze formaten.