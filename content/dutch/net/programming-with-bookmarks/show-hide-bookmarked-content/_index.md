---
title: Toon inhoud met bladwijzer verbergen in Word-document
linktitle: Toon inhoud met bladwijzer verbergen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u inhoud met bladwijzers dynamisch kunt weergeven of verbergen in Word-documenten met behulp van Aspose.Words voor .NET met deze uitgebreide stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Invoering

Hallo daar! Heeft u ooit de zichtbaarheid van specifieke inhoud in een Word-document willen controleren op basis van bepaalde voorwaarden? Met Aspose.Words voor .NET kunt u inhoud met bladwijzers dynamisch weergeven of verbergen met slechts een paar regels code. In deze zelfstudie begeleid ik u stap voor stap door het proces, zodat u elk onderdeel van de code begrijpt. Tegen het einde zul je een professional zijn in het manipuleren van bladwijzers in Word-documenten. Laten we beginnen!

## Vereisten

Voordat we ingaan op de tutorial, zorgen we ervoor dat je alles hebt wat je nodig hebt:

1. Basiskennis van C#: U moet vertrouwd zijn met de syntaxis en concepten van C#.
2.  Aspose.Words voor .NET: Download het[hier](https://releases.aspose.com/words/net/) . Als u nog niet klaar bent om te kopen, kunt u beginnen met a[gratis proefperiode](https://releases.aspose.com/).
3. Visual Studio: Elke recente versie zal werken, maar het gebruik van de nieuwste versie wordt aanbevolen.
4. .NET Framework: zorg ervoor dat het op uw computer is geïnstalleerd.

klaar om te beginnen? Geweldig! Laten we beginnen met het importeren van de benodigde naamruimten.

## Naamruimten importeren

Om Aspose.Words voor .NET te gebruiken, moeten we de vereiste naamruimten importeren. Deze stap zorgt ervoor dat we toegang hebben tot alle klassen en methoden die we gaan gebruiken.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Deze naamruimten zijn cruciaal voor het werken met Word-documenten en het manipuleren van de inhoud ervan.

## Stap 1: Het document instellen

Laten we eerst een nieuw Word-document en een documentbouwer maken. Met de documentbouwer kunnen we eenvoudig inhoud binnen het document toevoegen en manipuleren.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

In deze stap initialiseren we een nieuw document en een documentbuilder. Dit bereidt onze omgeving voor op verdere activiteiten.

## Stap 2: Inhoud met bladwijzer toevoegen

Vervolgens voegen we wat inhoud toe aan het document en maken we er een bladwijzer omheen. Deze bladwijzer helpt ons de inhoud te identificeren en te manipuleren.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Hier voegen we wat tekst toe voor en na de inhoud met een bladwijzer. De`StartBookmark`En`EndBookmark` methoden definiëren de grenzen van de bladwijzer.

## Stap 3: Een voorwaardelijk veld invoegen

Om de zichtbaarheid van de inhoud met een bladwijzer te bepalen, gebruiken we een voorwaardelijk veld. Dit veld controleert een voorwaarde en geeft de inhoud dienovereenkomstig weer of verbergt deze.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

In deze stap voegen we een IF-veld in dat de waarde van de bladwijzer controleert. Als de waarde "waar" is, wordt "Zichtbaar" weergegeven; anders wordt "Verborgen" weergegeven.

## Stap 4: Knooppunten herschikken

Vervolgens moeten we de knooppunten opnieuw rangschikken om ervoor te zorgen dat de voorwaardelijke logica correct wordt toegepast op de inhoud met een bladwijzer.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
    currentNode = nextNode;
}

Node endNode = bm.BookmarkEnd;
flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.FieldEnd)
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
    endNode = currentNode;
    currentNode = nextNode;
}
```

Hier verplaatsen we knooppunten om er zeker van te zijn dat de voorwaarde de inhoud met een bladwijzer op de juiste manier omvat.

## Stap 5: Afdruk samenvoegen uitvoeren

Ten slotte voeren we een samenvoegbewerking uit om de waarde van de bladwijzer in te stellen en te bepalen of de inhoud moet worden weergegeven of verborgen.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Met deze stap wordt de bladwijzerwaarde ingesteld op 'waar', waardoor de inhoud zichtbaar wordt op basis van onze voorwaarde.

## Stap 6: Het document opslaan

Na alle manipulaties is de laatste stap het opslaan van het gewijzigde document.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Hier slaan we het document op met een beschrijvende bestandsnaam om de wijzigingen aan te geven.

## Conclusie

 En dat is het! U hebt met succes geleerd hoe u inhoud met een bladwijzer in een Word-document kunt weergeven of verbergen met Aspose.Words voor .NET. Deze tutorial behandelde het maken van een document, het toevoegen van bladwijzers, het invoegen van voorwaardelijke velden, het herschikken van knooppunten en het uitvoeren van een samenvoegbewerking. Aspose.Words biedt een overvloed aan functies, dus aarzel niet om de[API-documentatie](https://reference.aspose.com/words/net/) voor meer geavanceerde mogelijkheden.

## Veelgestelde vragen

### 1. Wat is Aspose.Words voor .NET?

Aspose.Words voor .NET is een krachtige bibliotheek waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, wijzigen en converteren. Het wordt veel gebruikt voor documentautomatiseringstaken.

### 2. Kan ik Aspose.Words voor .NET gratis gebruiken?

 U kunt Aspose.Words voor .NET proberen met behulp van een[gratis proefperiode](https://releases.aspose.com/). Voor langdurig gebruik moet u een licentie aanschaffen.

### 3. Hoe wijzig ik andere eigenschappen van een bladwijzer?

 Met Aspose.Words kunt u verschillende eigenschappen van een bladwijzer manipuleren, zoals de tekst en locatie. Verwijs naar de[API-documentatie](https://reference.aspose.com/words/net/) voor gedetailleerde instructies.

### 4. Hoe krijg ik ondersteuning voor Aspose.Words voor .NET?

 kunt ondersteuning krijgen door naar de[Aspose-ondersteuningsforum](https://forum.aspose.com/c/words/8).

### 5. Kan ik andere soorten inhoud manipuleren met Aspose.Words voor .NET?

Ja, Aspose.Words voor .NET ondersteunt verschillende soorten inhoudsmanipulatie, waaronder tekst, afbeeldingen, tabellen en meer.