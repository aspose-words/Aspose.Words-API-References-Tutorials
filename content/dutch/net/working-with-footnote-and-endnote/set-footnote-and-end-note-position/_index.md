---
title: Voetnoot- en eindnootpositie instellen
linktitle: Voetnoot- en eindnootpositie instellen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u voetnoot- en eindnootposities in Word-documenten instelt met Aspose.Words voor .NET met deze gedetailleerde stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---
## Invoering

Als u met Word-documenten werkt en voetnoten en eindnoten effectief moet beheren, is Aspose.Words voor .NET uw favoriete bibliotheek. In deze zelfstudie leert u hoe u voetnoot- en eindnootposities in een Word-document instelt met behulp van Aspose.Words voor .NET. We zullen elke stap opsplitsen, zodat deze gemakkelijk te volgen en te implementeren is.

## Vereisten

Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u over het volgende beschikt:

-  Aspose.Words voor .NET-bibliotheek: u kunt het downloaden van[hier](https://releases.aspose.com/words/net/).
- Visual Studio: Elke recente versie werkt prima.
- Basiskennis van C#: als u de basisbeginselen begrijpt, kunt u deze eenvoudig volgen.

## Naamruimten importeren

Importeer eerst de benodigde naamruimten in uw C#-project:

```csharp
using System;
using Aspose.Words;
```

## Stap 1: Laad het Word-document

Om te beginnen moet u uw Word-document in het Aspose.Words Document-object laden. Hierdoor kunt u de inhoud van het document manipuleren.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Vervang in deze code`"YOUR DOCUMENT DIRECTORY"`met het daadwerkelijke pad waar uw document zich bevindt.

## Stap 2: Stel de voetnootpositie in

Vervolgens stelt u de positie van de voetnoten in. Met Aspose.Words voor .NET kunt u voetnoten onderaan de pagina of onder de tekst plaatsen.

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
```

 Hier hebben we ingesteld dat de voetnoten onder de tekst verschijnen. Als u ze liever onderaan de pagina heeft, gebruik dan`FootnotePosition.BottomOfPage`.

## Stap 3: Stel de eindnootpositie in

Op dezelfde manier kunt u de positie van eindnoten instellen. Eindnoten kunnen aan het einde van de sectie of aan het einde van het document worden geplaatst.

```csharp
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

 In dit voorbeeld worden eindnoten aan het einde van elke sectie geplaatst. Gebruik om ze aan het einde van het document te plaatsen`EndnotePosition.EndOfDocument`.

## Stap 4: Sla het document op

Sla ten slotte het document op om de wijzigingen toe te passen. Zorg ervoor dat u het juiste bestandspad en de juiste naam voor het uitvoerdocument opgeeft.

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Deze regel slaat het gewijzigde document op in de door u opgegeven map.

## Conclusie

Het instellen van voetnoot- en eindnootposities in Word-documenten met Aspose.Words voor .NET is eenvoudig zodra u de stappen kent. Door deze handleiding te volgen, kunt u uw documenten aanpassen aan uw behoeften, zodat voetnoten en eindnoten precies daar worden geplaatst waar u ze wilt hebben.

## Veelgestelde vragen

### Kan ik verschillende posities instellen voor individuele voetnoten of eindnoten?

Nee, Aspose.Words voor .NET stelt de positie voor alle voet- en eindnoten in een document op uniforme wijze in.

### Is Aspose.Words voor .NET compatibel met alle versies van Word-documenten?

Ja, Aspose.Words voor .NET ondersteunt een breed scala aan Word-documentformaten, waaronder DOC, DOCX, RTF en meer.

### Kan ik Aspose.Words voor .NET gebruiken met andere programmeertalen?

Aspose.Words voor .NET is ontworpen voor .NET-toepassingen, maar u kunt het gebruiken met elke door .NET ondersteunde taal, zoals C#, VB.NET, enz.

### Is er een gratis proefversie beschikbaar voor Aspose.Words voor .NET?

 Ja, u kunt een gratis proefperiode krijgen[hier](https://releases.aspose.com/).

### Waar kan ik meer gedetailleerde documentatie vinden voor Aspose.Words voor .NET?

 Gedetailleerde documentatie is beschikbaar[hier](https://reference.aspose.com/words/net/).