---
title: Detecteer nummering met witruimtes
linktitle: Detecteer nummering met witruimtes
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u lijstnummers met spaties kunt detecteren in Aspose.Words voor .NET. Verbeter eenvoudig de structuur van uw documenten.
type: docs
weight: 10
url: /nl/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
In deze zelfstudie verkennen we de C#-broncode voor de functie "Detectie van nummering met witruimten" met Aspose.Words voor .NET. Met deze functie kunt u lijsten detecteren en maken op basis van een tekstdocument met lijstnummers gevolgd door spaties.

## Stap 1: De omgeving instellen

Zorg ervoor dat u, voordat u begint, uw ontwikkelomgeving hebt ingesteld met Aspose.Words voor .NET. Zorg ervoor dat u de benodigde referenties hebt toegevoegd en de juiste naamruimten hebt geïmporteerd.

## Stap 2: Het tekstdocument maken

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

In deze stap maken we een tekstreeks die een tekstdocument simuleert met lijstnummers gevolgd door spaties. We gebruiken verschillende lijstscheidingstekens, zoals een punt, rechter haakje, opsommingsteken en witruimte.

## Stap 3: Uploadopties configureren

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 In deze stap configureren we de opties voor het laden van documenten. Wij creëren een nieuwe`TxtLoadOptions` bezwaar maken en instellen`DetectNumberingWithWhitespaces`eigendom aan`true`. Hierdoor kan Aspose.Words lijstnummers detecteren, zelfs als deze worden gevolgd door spaties.

## Stap 4: Het document laden en opslaan

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 In deze stap laden we het document met behulp van de opgegeven tekstreeks en laadopties. Wij gebruiken een`MemoryStream` om de tekstreeks naar een geheugenstroom te converteren. Vervolgens slaan we het resulterende document op in .docx-indeling.

### Voorbeeldbroncode voor de functie Detectie van witruimtenummering met Aspose.Words voor .NET.

```csharp

            
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Maak een document in platte tekst in de vorm van een string met delen die als lijsten kunnen worden geïnterpreteerd.
// Bij het laden worden de eerste drie lijsten altijd gedetecteerd door Aspose.Words,
// en Lijstobjecten worden na het laden voor hen gemaakt.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// De vierde lijst, met witruimte tussen het lijstnummer en de inhoud van het lijstitem,
// wordt alleen als lijst gedetecteerd als "DetectNumberingWithWhitespaces" in een LoadOptions-object is ingesteld op true,
// om te voorkomen dat alinea's die beginnen met getallen, ten onrechte als lijsten worden gedetecteerd.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Laad het document terwijl u LoadOptions als parameter toepast en verifieer het resultaat.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Nu kunt u de broncode uitvoeren om het tekstdocument met lijstnummers met spaties te laden en vervolgens een .docx-document maken met de gedetecteerde lijsten. Het uitvoerbestand wordt opgeslagen in de opgegeven map met de naam "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx".

## Conclusie
In deze zelfstudie hebben we de functie voor het detecteren van witruimtenummering in Aspose.Words voor .NET onderzocht. We hebben geleerd hoe we lijsten kunnen maken op basis van een tekstdocument met lijstnummers gevolgd door spaties.

Deze functie is uiterst handig voor het verwerken van documenten die lijstnummers bevatten die op verschillende manieren zijn opgemaakt. Door de juiste laadopties te gebruiken, kan Aspose.Words deze lijstnummers detecteren, zelfs als ze worden gevolgd door spaties, en deze omzetten in gestructureerde lijsten in het uiteindelijke document.

Het gebruik van deze functie kan u tijd besparen en de efficiëntie van uw workflow verbeteren. U kunt eenvoudig informatie uit tekstdocumenten halen en deze omzetten in goed gestructureerde documenten met de juiste lijsten.

Denk eraan om laadopties te overwegen, zoals het configureren van kiesdetectie voor witte ruimten, om de gewenste resultaten te bereiken.

Aspose.Words voor .NET biedt veel geavanceerde functies voor het manipuleren en genereren van documenten. Door de documentatie en voorbeelden van Aspose.Words verder te verkennen, kunt u de mogelijkheden van deze krachtige bibliotheek volledig benutten.

Aarzel dus niet om detectie van witruimtenummering te integreren in uw Aspose.Words voor .NET-projecten en profiteer van de voordelen ervan om goed gestructureerde en leesbare documenten te creëren.


