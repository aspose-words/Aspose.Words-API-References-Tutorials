---
title: Inhoudsopgave invoegen in Word-document
linktitle: Inhoudsopgave invoegen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een inhoudsopgave in Word-documenten kunt invoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/add-content-using-documentbuilder/insert-table-of-contents/
---
In deze uitgebreide zelfstudie leert u hoe u een inhoudsopgave in een Word-document kunt invoegen met Aspose.Words voor .NET. Wij begeleiden u door het proces en voorzien u van de benodigde C#-codefragmenten. Aan het einde van deze handleiding kunt u een inhoudsopgave genereren met de juiste kopjes en paginanummers.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Maak een nieuw document en DocumentBuilder
Maak om te beginnen een nieuw document met behulp van de klasse Document en initialiseer een DocumentBuilder-object:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg een inhoudsopgave in
Gebruik vervolgens de methode InsertTableOfContents van de klasse DocumentBuilder om een inhoudsopgave in te voegen. Geef de vereiste opmaakopties op binnen de methode:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Stap 3: Documentinhoud toevoegen
Voeg na het invoegen van de inhoudsopgave de daadwerkelijke documentinhoud toe. Stel de juiste kopstijlen in met StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Stap 4: Werk de inhoudsopgave bij
De nieuw ingevoegde inhoudsopgave zal aanvankelijk leeg zijn. Om het in te vullen, werkt u de velden in het document bij:

```csharp
doc.UpdateFields();
```

## Stap 5: Sla het document op
Nadat u de inhoudsopgave hebt ingevoegd en de velden hebt bijgewerkt, slaat u het document op in een bestand met behulp van de Save-methode van de Document-klasse:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Voorbeeldbroncode voor het invoegen van de inhoudsopgave met Aspose.Words voor .NET
Hier is de volledige broncode voor het invoegen van een inhoudsopgave met Aspose.Words voor .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialiseer DocumentBuilder met Document-object
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inhoudsopgave invoegen
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Begin met de daadwerkelijke documentinhoud op de tweede pagina.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// De nieuw ingevoegde inhoudsopgave zal aanvankelijk leeg zijn.
// Het moet worden ingevuld door de velden in het document bij te werken.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u een inhoudsopgave in een Word-document kunt invoegen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u nu een inhoudsopgave genereren met de juiste koppen en paginanummers voor uw documenten.

### Veelgestelde vragen over het invoegen van de inhoudsopgave in een Word-document

#### Vraag: Kan ik het uiterlijk van de inhoudsopgave aanpassen?

 A: Ja, u kunt het uiterlijk van de inhoudsopgave aanpassen door de opmaakopties te wijzigen die zijn opgegeven in het`InsertTableOfContents` methode. Met de parameters kunt u de paginanummers, inspringing en andere stijlen bepalen.

#### Vraag: Wat moet ik doen als ik specifieke kopniveaus wil opnemen in de inhoudsopgave?

 A: U kunt de gewenste kopniveaus opgeven die in de inhoudsopgave moeten worden opgenomen door de waarde binnen het aan te passen`InsertTableOfContents` methode. Gebruik bijvoorbeeld`"\\o \"1-3\""` omvat kopniveaus 1 tot en met 3.

#### Vraag: Kan ik de inhoudsopgave automatisch bijwerken als ik wijzigingen aanbreng in de documentinhoud?

 A: Ja, u kunt de inhoudsopgave automatisch bijwerken door te bellen naar`UpdateFields` methode op het document. Dit zorgt ervoor dat eventuele wijzigingen in de inhoud van het document, zoals het toevoegen of verwijderen van koppen, worden weerspiegeld in de inhoudsopgave.

#### Vraag: Hoe kan ik de kopniveaus in de inhoudsopgave anders opmaken?

 A: U kunt de kopniveaus verschillend opmaken door voor elk kopniveau verschillende alineastijlen te gebruiken. Door verschillende toe te wijzen`StyleIdentifier` waarden aan de`ParagraphFormat` van de`DocumentBuilder`, kunt u voor elk kopniveau verschillende stijlen maken.

#### Vraag: Is het mogelijk om extra opmaak toe te voegen aan de kopjes in de inhoudsopgave?

 A: Ja, u kunt extra opmaak toevoegen aan de koppen in de inhoudsopgave, zoals lettertypestijlen, kleuren of andere eigenschappen. Door het aanpassen van de`Font` eigenschappen van de`DocumentBuilder`, kunt u aangepaste opmaak toepassen op de koppen.