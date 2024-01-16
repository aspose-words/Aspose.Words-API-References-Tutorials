---
title: Schrijf alle CSS-regels in één bestand
linktitle: Schrijf alle CSS-regels in één bestand
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een Word-document naar vaste HTML converteert door alle CSS-regels in één bestand te schrijven met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Wanneer u een Word-document converteert naar vaste HTML in een C#-toepassing, wilt u wellicht alle CSS-regels consolideren in één bestand voor een betere organisatie en draagbaarheid. Met de Aspose.Words-bibliotheek voor .NET kunt u deze functionaliteit eenvoudig opgeven met behulp van de HtmlFixedSaveOptions-opslagopties. In deze stapsgewijze handleiding laten we u zien hoe u Aspose.Words voor .NET C#-broncode kunt gebruiken om een Word-document naar vaste HTML te converteren door alle CSS-regels in één bestand te schrijven met behulp van de opslagopties HtmlFixedSaveOptions.

## Inzicht in de Aspose.Words-bibliotheek

Voordat u in de code duikt, is het belangrijk dat u de Aspose.Words-bibliotheek voor .NET begrijpt. Aspose.Words is een krachtige bibliotheek voor het maken, bewerken, converteren en beschermen van Word-documenten op verschillende platforms, waaronder .NET. Het biedt veel functies voor het manipuleren van documenten, zoals het invoegen van tekst, het wijzigen van de opmaak, het toevoegen van secties en nog veel meer.

## Het Word-document laden

De eerste stap is het laden van het Word-document dat u naar vaste HTML wilt converteren. Gebruik de klasse Document om het document uit het bronbestand te laden. Hier is een voorbeeld :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

In dit voorbeeld laden we het document "Document.docx" in de documentenmap.

## Back-upopties configureren

De volgende stap is het configureren van de opslagopties voor het converteren naar vaste HTML. Gebruik de klasse HtmlFixedSaveOptions en stel de eigenschap SaveFontFaceCssSeparately in op false om alle CSS-regels in één bestand te schrijven. Hier leest u hoe u het moet doen:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

We maken een nieuw HtmlFixedSaveOptions-object en stellen de eigenschap SaveFontFaceCssSeparately in op false om alle CSS-regels in één bestand te schrijven.

## Vaste HTML-documentconversie

Nu we de opslagopties hebben geconfigureerd, kunnen we doorgaan met het converteren van het document naar vaste HTML. Gebruik de Save-methode van de Document-klasse om het geconverteerde document in een vast HTML-formaat op te slaan door opslagopties op te geven. Hier is een voorbeeld :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

In dit voorbeeld slaan we het geconverteerde document op als "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" met behulp van de opgegeven opslagopties.

### Voorbeeldbroncode voor HtmlFixedSaveOptions met de functie "Schrijf alle CSS-regels in één bestand" met behulp van Aspose.Words voor .NET

```csharp
// Toegangspad naar uw documentmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het Word-document
Document doc = new Document(dataDir + "Document.docx");

// Configureer back-upopties met de functie "Alle CSS-regels in één bestand schrijven".
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Converteer document naar vaste HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Conclusie

In deze handleiding hebben we besproken hoe u een Word-document naar vaste HTML kunt converteren door alle CSS-regels in één bestand te schrijven met behulp van HtmlFixedSaveOptions met de Aspose.Words-bibliotheek voor .NET. Door de meegeleverde stappen te volgen en de meegeleverde C#-broncode te gebruiken, kunt u deze functionaliteit eenvoudig toepassen in uw C#-applicatie. Door alle CSS-regels in één bestand te schrijven, wordt het eenvoudiger om de HTML-code die tijdens de documentconversie wordt gegenereerd, te organiseren en te beheren.