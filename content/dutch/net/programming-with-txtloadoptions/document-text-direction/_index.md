---
title: Documenttekstrichting
linktitle: Documenttekstrichting
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de tekstrichting in uw documenten kunt opgeven met Aspose.Words voor .NET. Verbeter de weergave voor talen die van rechts naar links worden geschreven.
type: docs
weight: 10
url: /nl/net/programming-with-txtloadoptions/document-text-direction/
---

In deze zelfstudie verkennen we de C#-broncode voor de functie "Documenttekstrichting" met Aspose.Words voor .NET. Met deze functie kunt u de richting van de tekst in een document opgeven, wat vooral handig is voor talen die van rechts naar links worden geschreven, zoals Hebreeuws of Arabisch.

## Stap 1: De omgeving instellen

Zorg ervoor dat u, voordat u begint, uw ontwikkelomgeving hebt ingesteld met Aspose.Words voor .NET. Zorg ervoor dat u de benodigde referenties hebt toegevoegd en de juiste naamruimten hebt geïmporteerd.

## Stap 2: Uploadopties configureren

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 In deze stap configureren we de opties voor het laden van documenten. Wij creëren een nieuwe`TxtLoadOptions` bezwaar maken en instellen`DocumentDirection`eigendom aan`DocumentDirection.Auto`. Deze waarde vertelt Aspose.Words om automatisch de tekstrichting te bepalen op basis van de inhoud van het document.

## Stap 3: Het document laden

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 In deze stap laden we het document met behulp van de`Document` methode en geef het pad door naar het tekstbestand dat moet worden geladen. Ook maken wij gebruik van de aangegeven laadmogelijkheden.

## Stap 4: Manipuleer de alinea en geef de tekstrichting weer

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 In deze stap hebben we toegang tot de eerste paragraaf van het document met behulp van de`FirstSection` En`Body` eigenschappen. Vervolgens hebben we toegang tot de`ParagraphFormat.Bidi` eigenschap om de tekstrichting van de alinea te bepalen. Deze waarde geven we vervolgens weer in de console.

## Stap 5: Sla het document op

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 In deze laatste stap slaan we het resulterende document op in .docx-indeling met behulp van de`Save` methode en geef het pad door aan het uitvoerbestand.

Nu kunt u de broncode uitvoeren om het tekstdocument te laden en de tekstrichting te bepalen. Het resulterende document wordt opgeslagen in de opgegeven map met de naam "WorkingWithTxtLoadOptions.DocumentTextDirection.docx".

### Voorbeeldbroncode voor functionaliteit voor documenttekstrichting met Aspose.Words voor .NET.


```csharp

            
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Conclusie

In deze zelfstudie hebben we de functie voor documenttekstrichting in Aspose.Words voor .NET onderzocht. We hebben geleerd hoe je de richting van tekst in een document kunt specificeren, vooral voor talen die van rechts naar links worden geschreven, zoals Hebreeuws of Arabisch.

Deze functie is essentieel om ervoor te zorgen dat tekst correct wordt weergegeven in meertalige documenten. Door de juiste laadopties te gebruiken, kan Aspose.Words automatisch de richting van de tekst detecteren en deze op het document toepassen.

Met Aspose.Words kunt u eenvoudig de richting van tekst in uw documenten manipuleren, waardoor gebruikers een soepele en intuïtieve leeservaring krijgen.

Het is belangrijk op te merken dat deze functie vooral handig is bij woordverwerking met talen die een specifieke tekstrichting vereisen. Aspose.Words maakt deze taak eenvoudig door krachtige hulpmiddelen te bieden om de richting van tekst in uw documenten te beheren.

Vergeet niet om de juiste laadopties te gebruiken, zoals het instellen van de automatische tekstrichting, om de gewenste resultaten in uw documenten te krijgen.

Aspose.Words voor .NET biedt veel geavanceerde functies voor het manipuleren en genereren van documenten. Door de documentatie en voorbeelden van Aspose.Words verder te verkennen, kunt u de mogelijkheden van deze krachtige bibliotheek volledig benutten.

Aarzel dus niet om de tekstrichting van documenten te integreren in uw Aspose.Words voor .NET-projecten en profiteer van de voordelen ervan om aantrekkelijke meertalige documenten van hoge kwaliteit te creëren.