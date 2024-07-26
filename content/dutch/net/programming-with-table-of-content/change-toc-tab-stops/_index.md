---
title: Wijzig de Toc-tabstops in een Word-document
linktitle: Wijzig de Toc-tabstops in een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de tabbladen met de inhoudsopgave in een Word-document kunt wijzigen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words voor .NET is een krachtige bibliotheek voor het maken, bewerken en manipuleren van Word-documenten in een C#-toepassing. Onder de functionaliteiten die Aspose.Words biedt, bestaat de mogelijkheid om de tabbladen te wijzigen die worden gebruikt in een inhoudsopgave van een Word-document. In deze handleiding laten we u zien hoe u de C#-broncode van Aspose.Words voor .NET kunt gebruiken om van tabblad te wisselen in de inhoudsopgave van een document.

## Inzicht in de Aspose.Words-bibliotheek

Voordat u in de code duikt, is het belangrijk dat u de Aspose.Words-bibliotheek voor .NET begrijpt. Aspose.Words is een populaire bibliotheek die het verwerken van woorden met Word-documenten eenvoudig en efficiënt maakt. Het biedt een breed scala aan functies voor het maken, bewerken en manipuleren van Word-documenten, inclusief het wijzigen van tabbladen met de inhoudsopgave.

## Het document met de inhoudsopgave laden

De eerste stap is het laden van het Word-document met de inhoudsopgave die u wilt wijzigen. Gebruik de klasse Document om het document uit het bronbestand te laden. Hier is een voorbeeld :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

In dit voorbeeld laden we het document "Inhoudsopgave.docx" in de documentenmap.

## Tabbladen in de inhoudsopgave wijzigen

Zodra het document is geladen, doorlopen we elke paragraaf van het document en controleren of deze is opgemaakt met behulp van de resultaatstijlen van de inhoudsopgave (TOC). Als dat zo is, passen we de tabbladen aan die worden gebruikt om de paginanummers uit te lijnen. Hier is hoe:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

In dit voorbeeld gebruiken we een lus om elke alinea in het document te doorlopen. Vervolgens controleren we of de alinea is opgemaakt met behulp van de inhoudsopgave-resultaatstijlen (TOC). Als dat het geval is, gaan we naar het eerste tabblad dat in deze paragraaf wordt gebruikt en passen we dit aan door het oude tabblad te verwijderen en een nieuw tabblad toe te voegen met een gewijzigde positie.

## Bewaar het gewijzigde document

Nadat u de nodige wijzigingen heeft aangebracht in de tabbladen in de inhoudsopgave, kunt u het gewijzigde document opslaan met de Save-methode van de Document-klasse. Hier is een voorbeeld :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

In dit voorbeeld slaan we het gewijzigde document op als "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### Voorbeeldbroncode voor de functie "Tabbladen met inhoudsopgave bewerken" met Aspose.Words voor .NET

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document met de inhoudsopgave
Document doc = new Document(dataDir + "Table of contents.docx");

// Wijzig de tabbladen van de inhoudsopgave
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Sla het gewijzigde document op
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Conclusie

In deze handleiding hebben we besproken hoe u Aspose.Words voor .NET kunt gebruiken om de tabbladen in de inhoudsopgave van een Word-document te wijzigen met behulp van de meegeleverde C#-broncode. Door de aangegeven stappen te volgen, kunt u eenvoudig de tabbladen met de inhoudsopgave in uw Word-documenten in uw C#-toepassing aanpassen. Aspose.Words biedt enorme flexibiliteit en kracht om te werken met de stijlen en opmaak van uw documenten, waardoor u aantrekkelijke en professionele Word-documenten kunt maken.

### Veelgestelde vragen over het wijzigen van tabbladstops in een Word-document

#### Vraag: Wat is het doel van de functionaliteit "Toc-tabstops wijzigen in Word-document" in Aspose.Words voor .NET?

A: Met de functionaliteit "Toc-tabstops in Word-document wijzigen" in Aspose.Words voor .NET kunt u de tabstops wijzigen die worden gebruikt in de inhoudsopgave van een Word-document. Hiermee kunt u de uitlijning en positionering van de paginanummers en bijbehorende koppen binnen de inhoudsopgave aanpassen.

#### Vraag: Wat is Aspose.Words voor .NET?

A: Aspose.Words voor .NET is een krachtige bibliotheek ontworpen voor woordenverwerking met Word-documenten in .NET-toepassingen. Het biedt uitgebreide functies voor het programmatisch maken, bewerken, manipuleren en converteren van Word-documenten met behulp van C# of andere .NET-talen.

#### Vraag: Hoe laad ik een Word-document met een inhoudsopgave met Aspose.Words voor .NET?

 A: Om een Word-document met een inhoudsopgave te laden met Aspose.Words voor .NET, kunt u de`Document` klasse en zijn constructor. Door het bestandspad van het document op te geven, kunt u het in een`Document` voorwerp. Hier is een voorbeeld:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Dit codefragment laadt het document "Inhoudsopgave.docx" in de opgegeven map.

#### Vraag: Hoe kan ik de tabbladen wijzigen die in de inhoudsopgave worden gebruikt met Aspose.Words voor .NET?

A: Zodra het document is geladen, kunt u elke alinea van het document doorlopen en controleren of het is opgemaakt met de resultaatstijlen van de inhoudsopgave (TOC). Als een alinea is opgemaakt als inhoudsopgavestijl, kunt u de tabbladen wijzigen die worden gebruikt om de paginanummers uit te lijnen. In Aspose.Words voor .NET hebt u toegang tot de`ParagraphFormat` eigenschap van elke alinea om de tabstops op te halen en te wijzigen. Hier is een voorbeeld:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        TabStop tab = para.ParagraphFormat.TabStops[0];
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }
}
```

In deze code loopt de lus door elke alinea in het document. Als een alinea een inhoudsopgavestijl heeft, wordt toegang verkregen tot de eerste tabstop die in die alinea wordt gebruikt, wordt deze verwijderd en wordt een nieuwe tabstop met een gewijzigde positie toegevoegd.

#### Vraag: Kan ik de tabbladen voor meerdere niveaus in de inhoudsopgave wijzigen met Aspose.Words voor .NET?

A: Ja, u kunt de tabbladen voor meerdere niveaus in de inhoudsopgave wijzigen met Aspose.Words voor .NET. Door elke alinea te doorlopen en de inhoudsopgavestijl te controleren, kunt u de tabbladen voor elk niveau afzonderlijk aanpassen. U kunt toegang krijgen tot het gewenste niveau van de inhoudsopgave en de tabstops dienovereenkomstig aanpassen.

#### Vraag: Hoe sla ik het gewijzigde document op nadat ik de tabbladen in de inhoudsopgave heb gewijzigd met Aspose.Words voor .NET?

 A: Nadat u de nodige wijzigingen heeft aangebracht in de tabbladen in de inhoudsopgave, kunt u het gewijzigde document opslaan met behulp van de`Save` werkwijze van de`Document` klas. Geef het gewenste bestandspad en de gewenste naam voor het uitvoerdocument op als parameter voor het`Save` methode. Hier is een voorbeeld:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Met deze code wordt het gewijzigde document opgeslagen als "WorkingWithTableOfContent.ChangeTocTabStops.docx".

#### Vraag: Kan ik andere aspecten van de inhoudsopgave aanpassen met Aspose.Words voor .NET?

A: Ja, met Aspose.Words voor .NET kunt u verschillende aspecten van de inhoudsopgave aanpassen. Naast het wijzigen van de tabbladen kunt u ook de lettertypestijlen, grootte, uitlijning en andere opmaakeigenschappen van de inhoudsopgave-items en paginanummers wijzigen. Bovendien kunt u de inspringing, de afstand en de opmaak van de overeenkomstige koppen aanpassen.

#### Q:. Kan ik de tabuitlijning en aanlooptekens voor de inhoudsopgave wijzigen met Aspose.Words voor .NET?

A: Ja, u kunt de tabuitlijning en aanlooptekens voor de inhoudsopgave wijzigen met Aspose.Words voor .NET. Door de tabstops te openen en hun uitlijnings- en verwijslijneigenschappen aan te passen, kunt u de uitlijning en visuele weergave van de paginanummers en bijbehorende koppen in de inhoudsopgave bepalen.

#### Vraag: Ondersteunt Aspose.Words voor .NET het wijzigen van andere stijlen en opmaak in Word-documenten?

A: Ja, Aspose.Words voor .NET biedt uitgebreide ondersteuning voor het wijzigen van verschillende stijlen en opmaak in Word-documenten. Hiermee kunt u stijlen wijzigen voor verschillende elementen, zoals alinea's, koppen, tabellen, lijsten en meer. U kunt lettertypen, kleuren, uitlijning, inspringing, spatiëring en andere opmaakaspecten naar wens wijzigen.

#### Vraag: Kan ik de tabbladen in de inhoudsopgave van een bestaand Word-document wijzigen met Aspose.Words voor .NET?

A: Ja, u kunt de tabbladen in de inhoudsopgave van een bestaand Word-document wijzigen met Aspose.Words voor .NET. Door het document te laden, de alinea's te doorlopen en de nodige wijzigingen aan te brengen in de tabstops, kunt u de tabbladen in de inhoudsopgave bijwerken. Sla ten slotte het document op om de wijzigingen toe te passen.