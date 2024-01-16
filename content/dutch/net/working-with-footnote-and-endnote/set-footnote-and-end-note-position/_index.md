---
title: Voetnoot- en eindnootpositie instellen
linktitle: Voetnoot- en eindnootpositie instellen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de positie van voetnoten en eindnoten in Word-documenten instelt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

In deze stapsgewijze zelfstudie laten we u zien hoe u Aspose.Words voor .NET kunt gebruiken om de positie van voetnoten en eindnoten in een Word-document in te stellen. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze in uw eigen projecten kunt implementeren.

 Om aan de slag te gaan, moet u ervoor zorgen dat Aspose.Words voor .NET is geïnstalleerd en ingesteld in uw ontwikkelomgeving. Als u dit nog niet hebt gedaan, downloadt en installeert u de bibliotheek van[Aspose.Releases]https://releases.aspose.com/words/net/.

## Stap 1: Het documentobject initialiseren

 Initialiseer eerst de`Document` object door het pad naar uw brondocument op te geven:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Stap 2: Voetnoot- en eindnootpositie instellen

 Ga vervolgens naar de`FootnoteOptions` En`EndnoteOptions` eigenschappen van het document om de positie van voetnoten en eindnoten in te stellen. In dit voorbeeld stellen we de positie van de voetnoten in op onder de tekst en de positie van de eindnoten op het einde van de sectie:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Stap 3: Het document opslaan

Sla ten slotte het gewijzigde document op:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Dat is het! U hebt met succes de positie van voetnoten en eindnoten in een Word-document ingesteld met Aspose.Words voor .NET.

### Voorbeeldbroncode voor voetnoot- en eindnootpositie instellen met Aspose.Words voor .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

U kunt deze code gerust in uw eigen projecten gebruiken en aanpassen aan uw specifieke vereisten.

### Veelgestelde vragen

#### Vraag: Hoe kan ik voetnoten en eindnoten positioneren in Aspose.Words?

 A: Om voetnoten en eindnoten in Aspose.Words te positioneren, moet u de`FootnoteOptions` klasse en de`Position` eigendom. U kunt deze eigenschap instellen op elke gewenste waarde, zoals`BottomOfPage` (onderaan de pagina) of`EndOfSection` (aan het einde van het gedeelte).

#### Vraag: Is het mogelijk om de positie van voetnoten en eindnoten voor elke pagina of sectie van het document aan te passen?

A: Ja, het is mogelijk om de positie van voetnoten en eindnoten voor elke pagina of sectie van het document aan te passen. U kunt de sectie- en paginamanipulatiemethoden van Aspose.Words gebruiken om specifieke posities voor voetnoten en eindnoten te definiëren.

#### Vraag: Hoe verwijder ik voetnoten of eindnoten uit een document?

 A: Om voetnoten of eindnoten uit een document in Aspose.Words te verwijderen, kunt u geschikte methoden gebruiken, zoals`RemoveAllFootnotes` om alle voetnoten te verwijderen of`RemoveAllEndnotes` om alle eindnoten te verwijderen. Zorg ervoor dat u het document opslaat nadat u deze handelingen heeft uitgevoerd.

#### Vraag: Kunnen voetnoten en eindnoten buiten de paginamarges worden geplaatst?

Nee, voetnoten en eindnoten kunnen standaard niet buiten de paginamarges in Aspose.Words worden geplaatst. Indien nodig kunt u de documentmarges echter aanpassen om meer ruimte voor voet- en eindnoten vrij te maken.

#### Vraag: Kunnen voetnoten en eindnoten worden aangepast met een specifiek lettertype of opmaakstijl?

A: Ja, u kunt voetnoten en eindnoten aanpassen met specifieke lettertypen of opmaakstijlen in Aspose.Words. U kunt de beschikbare methoden en eigenschappen gebruiken om lettertypestijlen, kleuren, lettergroottes, enz. toe te passen op voetnoten en eindnoten.