---
title: Verwijder bronkopteksten en voetteksten
linktitle: Verwijder bronkopteksten en voetteksten
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u kop- en voetteksten in Word-documenten verwijdert met Aspose.Words voor .NET. Vereenvoudig uw documentbeheer met onze stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/remove-source-headers-footers/
---
## Invoering

In deze uitgebreide handleiding gaan we dieper in op hoe u kop- en voetteksten effectief uit een Word-document kunt verwijderen met behulp van Aspose.Words voor .NET. Kop- en voetteksten worden vaak gebruikt voor paginanummering, documenttitels of andere herhalende inhoud in Word-documenten. Of u nu documenten samenvoegt of de opmaak opruimt, als u dit proces beheerst, kunt u uw documentbeheertaken stroomlijnen. Laten we het stapsgewijze proces verkennen om dit te bereiken met behulp van Aspose.Words voor .NET.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Ontwikkelomgeving: Zorg ervoor dat Visual Studio of een andere .NET-ontwikkelomgeving is geïnstalleerd.
2.  Aspose.Words voor .NET: Zorg ervoor dat u Aspose.Words voor .NET hebt gedownload en geïnstalleerd. Zo niet, dan kun je het krijgen van[hier](https://releases.aspose.com/words/net/).
3. Basiskennis: Bekendheid met programmeren in C# en de basisprincipes van .NET Framework.

## Naamruimten importeren

Zorg ervoor dat u, voordat u begint met coderen, de benodigde naamruimten in uw C#-bestand importeert:

```csharp
using Aspose.Words;
```

## Stap 1: Laad het brondocument

Eerst moet u het brondocument laden waarvan u kop- en voetteksten wilt verwijderen. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap waar het brondocument zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## Stap 2: Maak of laad het bestemmingsdocument

 Als u nog geen doeldocument heeft gemaakt waarin u de gewijzigde inhoud wilt plaatsen, kunt u een nieuw document maken`Document` object of laad een bestaand object.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Stap 3: Kop- en voetteksten uit secties wissen

Doorloop elke sectie in het brondocument (`srcDoc`) en wis de kop- en voetteksten.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Stap 4: Beheer de LinkToPrevious-instelling

Om te voorkomen dat kop- en voetteksten doorgaan in het doeldocument (`dstDoc` ), zorg ervoor dat de`LinkToPrevious` instelling voor kop- en voetteksten is ingesteld op`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Stap 5: Voeg het gewijzigde document toe aan het doeldocument

Voeg ten slotte de gewijzigde inhoud uit het brondocument toe (`srcDoc`) naar het bestemmingsdocument (`dstDoc`) met behoud van de bronopmaak.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 6: Sla het resulterende document op

Sla het definitieve document met verwijderde kop- en voetteksten op in de door u opgegeven map.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

## Conclusie

Het verwijderen van kop- en voetteksten uit een Word-document met Aspose.Words voor .NET is een eenvoudig proces dat de documentbeheertaken aanzienlijk kan verbeteren. Door de hierboven beschreven stappen te volgen, kunt u documenten efficiënt opruimen voor een verzorgde, professionele uitstraling.

## Veelgestelde vragen

### Kan ik kop- en voetteksten alleen uit specifieke secties verwijderen?
Ja, u kunt secties doorlopen en kop- en voetteksten selectief wissen als dat nodig is.

### Ondersteunt Aspose.Words voor .NET het verwijderen van kop- en voetteksten in meerdere documenten?
Absoluut, u kunt kop- en voetteksten in meerdere documenten manipuleren met Aspose.Words voor .NET.

###  Wat gebeurt er als ik vergeet in te stellen`LinkToPrevious` to `false`?
Kop- en voetteksten uit het brondocument kunnen doorlopen in het doeldocument.

### Kan ik kop- en voetteksten programmatisch verwijderen zonder andere opmaak te beïnvloeden?
Ja, met Aspose.Words voor .NET kunt u kop- en voetteksten verwijderen terwijl de rest van de opmaak van het document behouden blijft.

### Waar kan ik meer bronnen en ondersteuning vinden voor Aspose.Words voor .NET?
 Bezoek de[Aspose.Words voor .NET-documentatie](https://reference.aspose.com/words/net/) voor gedetailleerde API-referenties en voorbeelden.
