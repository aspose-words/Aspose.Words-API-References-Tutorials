---
title: Ontkoppel kopteksten en voetteksten
linktitle: Ontkoppel kopteksten en voetteksten
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u kop- en voetteksten in Word-documenten ontkoppelt met Aspose.Words voor .NET. Volg onze gedetailleerde, stapsgewijze handleiding om documentmanipulatie onder de knie te krijgen.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/unlink-headers-footers/
---
## Invoering

In de wereld van documentverwerking kan het consistent houden van kop- en voetteksten soms een uitdaging zijn. Of u nu documenten samenvoegt of gewoon verschillende kop- en voetteksten voor verschillende secties wilt hebben, het is essentieel dat u weet hoe u deze kunt ontkoppelen. Vandaag gaan we dieper in op hoe u dit kunt bereiken met Aspose.Words voor .NET. We leggen het stap voor stap uit, zodat u het gemakkelijk kunt volgen. Klaar om documentmanipulatie onder de knie te krijgen? Laten we beginnen!

## Vereisten

Voordat we in de kern duiken, zijn er een paar dingen die je nodig hebt:

-  Aspose.Words voor .NET-bibliotheek: u kunt het downloaden van de[Aspose-releasespagina](https://releases.aspose.com/words/net/).
- .NET Framework: Zorg ervoor dat u een compatibel .NET-framework hebt geïnstalleerd.
- IDE: Visual Studio of een andere .NET-compatibele geïntegreerde ontwikkelomgeving.
- Basiskennis van C#: Je hebt een basiskennis van de programmeertaal C# nodig.

## Naamruimten importeren

Om aan de slag te gaan, moet u ervoor zorgen dat u de benodigde naamruimten in uw project importeert. Hierdoor krijgt u toegang tot de Aspose.Words-bibliotheek en zijn functies.

```csharp
using Aspose.Words;
```

Laten we het proces opsplitsen in beheersbare stappen om u te helpen kop- en voetteksten in uw Word-documenten te ontkoppelen.

## Stap 1: Stel uw project in

Eerst moet u uw projectomgeving instellen. Open uw IDE en maak een nieuw .NET-project. Voeg een verwijzing toe naar de Aspose.Words-bibliotheek die u eerder hebt gedownload.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het brondocument

Vervolgens moet u het brondocument laden dat u wilt wijzigen. De kop- en voetteksten van dit document zijn ontkoppeld.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## Stap 3: Laad het bestemmingsdocument

Laad nu het doeldocument waar u het brondocument wilt toevoegen nadat u de kop- en voetteksten hebt ontkoppeld.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Stap 4: Ontkoppel kop- en voetteksten

 Deze stap is cruciaal. Om de kop- en voetteksten van het brondocument te ontkoppelen van die van het doeldocument, gebruikt u de`LinkToPrevious` methode. Deze methode zorgt ervoor dat de kop- en voetteksten niet worden overgedragen naar het bijgevoegde document.

```csharp
// Ontkoppel de kop- en voetteksten in het brondocument om dit te stoppen
//van het voortzetten van de kop- en voetteksten van het doeldocument.
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Stap 5: Voeg het brondocument toe

 Nadat u de kop- en voetteksten hebt ontkoppeld, kunt u het brondocument aan het doeldocument toevoegen. Gebruik de`AppendDocument` methode en stel de importformaatmodus in op`KeepSourceFormatting` om de oorspronkelijke opmaak van het brondocument te behouden.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 6: Bewaar het definitieve document

Sla ten slotte het nieuw gemaakte document op. Aan dit document wordt de inhoud van het brondocument toegevoegd aan het doeldocument, waarbij de kop- en voetteksten zijn ontkoppeld.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

## Conclusie

En daar heb je het! Door deze stappen te volgen, hebt u met succes de kop- en voetteksten in uw brondocument ontkoppeld en deze aan uw doeldocument toegevoegd met Aspose.Words voor .NET. Deze techniek kan met name handig zijn als u met complexe documenten werkt waarvoor verschillende kop- en voetteksten voor verschillende secties nodig zijn. Veel codeerplezier!

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?  
Aspose.Words voor .NET is een krachtige bibliotheek voor het werken met Word-documenten in .NET-toepassingen. Hiermee kunnen ontwikkelaars programmatisch documenten maken, wijzigen, converteren en afdrukken.

### Kan ik kop- en voetteksten alleen voor specifieke secties ontkoppelen?  
 Ja, u kunt kop- en voetteksten voor specifieke secties ontkoppelen door naar de`HeadersFooters` eigenschap van de gewenste sectie en gebruik de`LinkToPrevious` methode.

### Is het mogelijk om de originele opmaak van het brondocument te behouden?  
 Ja, gebruik bij het toevoegen van het brondocument de`ImportFormatMode.KeepSourceFormatting` optie om de originele opmaak te behouden.

### Kan ik Aspose.Words voor .NET gebruiken met andere .NET-talen dan C#?  
Absoluut! Aspose.Words voor .NET kan worden gebruikt met elke .NET-taal, inclusief VB.NET en F#.

### Waar kan ik meer documentatie en ondersteuning vinden voor Aspose.Words voor .NET?  
 Uitgebreide documentatie vindt u op de website[Aspose.Words voor .NET-documentatiepagina](https://reference.aspose.com/words/net/) en ondersteuning is beschikbaar op de[Aspose-forum](https://forum.aspose.com/c/words/8).
