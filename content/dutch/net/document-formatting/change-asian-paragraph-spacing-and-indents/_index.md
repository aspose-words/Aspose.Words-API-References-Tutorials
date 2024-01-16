---
title: Wijzig de Aziatische alinea-afstand en inspringingen in een Word-document
linktitle: Wijzig de Aziatische alinea-afstand en inspringingen in een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de Aziatische alinea-afstand en inspringingen in een Word-document kunt wijzigen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
In deze zelfstudie laten we u zien hoe u de afstand en inspringingen van een Aziatische alinea kunt wijzigen met Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en de wijzigingen toe te passen.

## Stap 1: Het document laden

Om te beginnen geeft u de directory voor uw documenten op en laadt u het document met de Aziatische typografie in een Document-object. Hier is hoe:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Stap 2: De alinea-afstand en inspringingen wijzigen

We zullen nu de spatiëring en inspringingen van de eerste alinea van het Aziatische document wijzigen. Hier is hoe:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Update ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Update ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //Update ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Update ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Update ParagraphFormat.SpaceAfter
```

## Stap 3: Het document opslaan

 Nadat u het tekstinvoerformulierveld hebt ingevoegd, slaat u het document op de gewenste locatie op met behulp van de`Save` methode. Zorg ervoor dat u het juiste bestandspad opgeeft:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Voorbeeldbroncode voor het wijzigen van de Aziatische alinea-afstand en inspringingen met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie Aziatische alinea-afstand en inspringingen bewerken met Aspose.Words voor .NET:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent wordt bijgewerkt
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent wordt bijgewerkt
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent wordt bijgewerkt
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore wordt bijgewerkt
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter wordt bijgewerkt

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

Met deze code kun je de afstand en inspringingen van een Aziatische alinea wijzigen met Aspose.Words voor .NET.

## Conclusie

 In deze zelfstudie hebben we geleerd hoe u de afstand en inspringingen van een Aziatische alinea kunt wijzigen met Aspose.Words voor .NET. Door de relevante eigenschappen van de`ParagraphFormat`kunnen we de lay-out en het uiterlijk van Aziatische alinea's in een Word-document bepalen. Deze functie is handig voor het aanpassen van de opmaak van tekst met Aziatische tekens en het bereiken van de gewenste visuele presentatie in documenten met gemengde taalinhoud.

### Veelgestelde vragen

#### Vraag: Wat doet de functie "Aziatische alinea-afstand en inspringingen wijzigen" in Aspose.Words voor .NET?

A: Met de functie "Aziatische alinea-afstand en inspringingen wijzigen" in Aspose.Words voor .NET kunt u de afstand- en inspringingseigenschappen van een Aziatische alinea in een Word-document wijzigen. U kunt de waarden voor de linker- en rechterinspringing, de inspringing van de eerste regel, de spatie vóór en de spatie na aanpassen om de lay-out en het uiterlijk van de alinea te bepalen.

#### Vraag: Hoe wijzig ik de afstand en inspringingen van een Aziatische alinea met Aspose.Words voor .NET?

 A: Om de afstand en inspringingen van een Aziatische alinea te wijzigen, moet u naar het`ParagraphFormat`van de doelparagraaf en wijzig de relevante eigenschappen ervan. In de gegeven voorbeeldcode openen we de eerste alinea van het document en stellen we de`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , En`LineUnitAfter` eigenschappen om de afstand en inspringingen aan te passen.

#### Vraag: Kan ik deze wijzigingen toepassen op andere paragrafen in het document?

 A: Ja, u kunt deze wijzigingen toepassen op andere paragrafen in het document door naar hun respectievelijke paragrafen te gaan`ParagraphFormat` voorwerpen. De voorbeeldcode richt zich op de eerste alinea van het document, maar u kunt andere alinea's wijzigen door de index in het bestand aan te passen`Paragraphs` verzameling of gebruik andere criteria om de gewenste alinea's te selecteren.