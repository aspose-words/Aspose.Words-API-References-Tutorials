---
title: Gebruik het lettertype van de doelmachine
linktitle: Gebruik het lettertype van de doelmachine
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een Word-document naar vaste HTML converteert met behulp van de lettertypen van de doelmachine met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Wanneer u een Word-document naar vaste HTML converteert in een C#-toepassing, wilt u wellicht de lettertypen van de doelmachine gebruiken om ervoor te zorgen dat de weergegeven HTML het oorspronkelijke uiterlijk en de oorspronkelijke stijl van het document behoudt. Met de Aspose.Words-bibliotheek voor .NET kunt u deze functionaliteit eenvoudig opgeven met behulp van de HtmlFixedSaveOptions-opslagopties. In deze stapsgewijze handleiding laten we u zien hoe u de C#-broncode van Aspose.Words voor .NET kunt gebruiken om een Word-document naar vaste HTML te converteren met behulp van de lettertypen van de doelmachine met behulp van de HtmlFixedSaveOptions.

## Inzicht in de Aspose.Words-bibliotheek

Voordat u in de code duikt, is het belangrijk dat u de Aspose.Words-bibliotheek voor .NET begrijpt. Aspose.Words is een krachtige bibliotheek voor het maken, bewerken, converteren en beschermen van Word-documenten op verschillende platforms, waaronder .NET. Het biedt veel functies voor het manipuleren van documenten, zoals het invoegen van tekst, het wijzigen van de opmaak, het toevoegen van secties en nog veel meer.

## Het Word-document laden

De eerste stap is het laden van het Word-document dat u naar vaste HTML wilt converteren. Gebruik de klasse Document om het document uit het bronbestand te laden. Hier is een voorbeeld :

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

In dit voorbeeld laden we het document "Opsommingstekens met alternatief lettertype.docx" in de documentenmap.

## Back-upopties configureren

De volgende stap is het configureren van de opslagopties voor het converteren naar vaste HTML. Gebruik de klasse HtmlFixedSaveOptions en stel de eigenschap UseTargetMachineFonts in op true om Aspose.Words te vertellen lettertypen van de doelmachine te gebruiken. Hier leest u hoe u het moet doen:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

We maken een nieuw HtmlFixedSaveOptions-object en stellen de eigenschap UseTargetMachineFonts in op true om de lettertypen van de doelmachine te gebruiken bij het converteren.

## Vaste HTML-documentconversie

Nu we de opslagopties hebben geconfigureerd, kunnen we doorgaan met het converteren van het document naar vaste HTML. Gebruik de Save-methode van de Document-klasse om het geconverteerde document in een vast HTML-formaat op te slaan door opslagopties op te geven. Hier is een voorbeeld :

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

In dit voorbeeld slaan we het geconverteerde document op als "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" met behulp van de opgegeven opslagopties.

### Voorbeeldbroncode voor HtmlFixedSaveOptions met de functie "Gebruik lettertypen van doelmachine" met behulp van Aspose.Words voor .NET

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het Word-document
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//Configureer back-upopties met de functie "Gebruik lettertypen van doelcomputer".
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Converteer document naar vaste HTML
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Conclusie

In deze handleiding hebben we uitgelegd hoe u een Word-document naar vaste HTML kunt converteren met behulp van de lettertypen van de doelmachine met de Aspose.Words-bibliotheek voor .NET. Door de meegeleverde stappen te volgen en de meegeleverde C#-broncode te gebruiken, kunt u deze functionaliteit eenvoudig toepassen in uw C#-applicatie. De conversie naar vaste HTML met de lettertypen van de doelmachine garandeert een getrouwe en consistente weergave van het document in HTML-formaat.
