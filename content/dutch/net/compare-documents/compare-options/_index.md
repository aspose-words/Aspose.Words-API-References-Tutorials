---
title: Vergelijk opties in Word-document
linktitle: Vergelijk opties in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het uitleggen van de C#-broncode van de vergelijkingsopties in de Word-documentfunctie met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/compare-documents/compare-options/
---
In deze zelfstudie leggen we uit hoe u de functie Vergelijkingsopties in Word-documenten gebruikt met Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en de wijzigingen toe te passen.

## Stap 1: Vergelijk documenten met aangepaste opties

 Laad om te beginnen twee documenten om te vergelijken. In dit voorbeeld gebruiken we de`Clone()` methode om een kopie van het originele document te maken. Hier is hoe:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Stap 2: Vergelijkingsopties configureren

 We zullen nu de vergelijkingsopties configureren door een`CompareOptions` object en stel indien nodig de verschillende eigenschappen in. Hier is hoe:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Stap 3: Vergelijk documenten met aangepaste opties

 We zullen nu gebruik maken van de`Compare()` methode waarbij de aangepaste opties worden doorgegeven om de twee documenten te vergelijken. Deze methode markeert de wijzigingen in het originele document. Hier is hoe:

```csharp
// Vergelijk documenten met aangepaste opties
docA.Compare(docB, "user", DateTime.Now, options);

// Controleer of de documenten gelijk zijn
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Voorbeeldbroncode voor vergelijkingsopties met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie Vergelijk opties met Aspose.Words voor .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Met deze code kunt u twee documenten vergelijken met behulp van aangepaste opties om specifieke elementen te negeren bij het vergelijken met Aspose.Words voor .NET.

## Conclusie

In deze zelfstudie hebben we geleerd hoe u de vergelijkingsopties in Aspose.Words voor .NET kunt gebruiken om het vergelijkingsproces aan te passen bij het vergelijken van twee documenten. Door verschillende opties op te geven, kunt u specifieke elementen negeren en het vergelijkingsproces flexibeler maken. Met deze functie heeft u meer controle over het vergelijkingsproces en kunt u dit afstemmen op uw specifieke vereisten. Aspose.Words voor .NET biedt krachtige mogelijkheden voor documentvergelijking, waardoor het gemakkelijk wordt om verschillen tussen documenten te identificeren en bepaalde elementen indien nodig te negeren.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het gebruik van vergelijkingsopties in Aspose.Words voor .NET?

A: Met de vergelijkingsopties in Aspose.Words voor .NET kunt u het vergelijkingsproces aanpassen wanneer u twee documenten vergelijkt. Met deze opties kunt u opgeven welke elementen u tijdens de vergelijking moet negeren, zoals wijzigingen in de opmaak, kop- en voetteksten, tabellen, velden, opmerkingen, tekstvakken en voetnoten.

#### Vraag: Hoe gebruik ik vergelijkingsopties in Aspose.Words voor .NET?

A: Volg deze stappen om vergelijkingsopties in Aspose.Words voor .NET te gebruiken:
1. Laad de twee documenten die u wilt vergelijken in afzonderlijke documentobjecten.
2.  Gebruik de`Clone()` methode om een kopie van het originele document te maken.
3.  Maak een`CompareOptions` object en stel de eigenschappen ervan in om het vergelijkingsproces aan te passen. U kunt opgeven welke elementen u tijdens de vergelijking moet negeren.
4.  Gebruik de`Compare()` methode op een van de documenten en geef het andere document en de`CompareOptions` object als parameters. Deze methode vergelijkt de documenten op basis van de opgegeven opties en markeert de wijzigingen in het originele document.
5.  Controleer de`Revisions` eigendom van het originele document. Als de telling nul is, betekent dit dat de documenten identiek zijn, rekening houdend met de opgegeven opties.

#### Vraag: Wat zijn de gebruikelijke opties die beschikbaar zijn in CompareOptions?

A: De gebruikelijke opties die beschikbaar zijn in CompareOptions zijn onder meer:
- `IgnoreFormatting`: Negeert wijzigingen in de opmaak.
- `IgnoreHeadersAndFooters`: Negeert wijzigingen in kop- en voetteksten.
- `IgnoreCaseChanges`: Negeert hoofdletterwijzigingen (hoofdletters/kleine letters).
- `IgnoreTables`: Negeert wijzigingen in tabellen.
- `IgnoreFields`: Negeert wijzigingen in velden.
- `IgnoreComments`: negeert wijzigingen in opmerkingen.
- `IgnoreTextboxes`Negeert wijzigingen in tekstvakken.
- `IgnoreFootnotes`: Negeert wijzigingen in voetnoten.

#### Vraag: Kan ik aangepaste opties gebruiken voor specifieke elementen tijdens documentvergelijking?

 A: Ja, u kunt tijdens documentvergelijking aangepaste opties voor specifieke elementen gebruiken. Door de eigenschappen van de`CompareOptions` dienovereenkomstig bezwaar maakt, kunt u kiezen welke elementen u wilt negeren en welke u tijdens de vergelijking in overweging wilt nemen.