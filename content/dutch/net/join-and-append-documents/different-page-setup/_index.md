---
title: Verschillende pagina-instellingen
linktitle: Verschillende pagina-instellingen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een document met verschillende pagina-instellingen kunt toevoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/different-page-setup/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET kunt gebruiken om een document met verschillende pagina-instellingen aan een ander document toe te voegen. De meegeleverde broncode laat zien hoe u verschillende pagina-instellingen voor de bron- en doeldocumenten kunt instellen en hoe u voor de juiste voortzetting en nummering kunt zorgen.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

-  Aspose.Words voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van[Aspose.Releases]https://releases.aspose.com/words/net/ of gebruik NuGet-pakketbeheer om het te installeren.
- Een documentmappad waar de bron- en doeldocumenten zich bevinden.

## Stap 2: Open de bron- en doeldocumenten

 Open de bron- en doeldocumenten met behulp van de`Document` klasse constructeur. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Stap 3: Stel pagina-instellingen in voor het brondocument

 Pas de pagina-instellingen van het brondocument aan om een goede voortzetting en nummering te garanderen. In dit voorbeeld stellen we het begin van de sectie in op`SectionStart.Continuous` en start de paginanummering opnieuw. We zorgen er ook voor dat de paginabreedte, hoogte en richting overeenkomen met het laatste gedeelte van het bestemmingsdocument.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Stap 4: Pas de alineaopmaak aan

 Om de juiste opmaak te behouden, doorloopt u alle alinea's in het brondocument en stelt u de`KeepWithNext`eigendom aan`true`Dit zorgt ervoor dat alinea's bij elkaar blijven tijdens het toevoegproces.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Stap 5: Voeg het brondocument toe aan het doeldocument

 Gebruik de`AppendDocument` methode van het doeldocument om het gewijzigde brondocument aan het doeldocument toe te voegen, waarbij de bronopmaak behouden blijft.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 6: Sla het bestemmingsdocument op

 Sla ten slotte het gewijzigde bestemmingsdocument op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Hiermee is de implementatie voltooid van het toevoegen van een document met verschillende pagina-instellingen met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor verschillende pagina-instellingen met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Stel het brondocument zo in dat het direct na het einde van het bestemmingsdocument verdergaat.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Begin de paginanummering opnieuw aan het begin van het brondocument.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Om er zeker van te zijn dat dit niet gebeurt als het brondocument verschillende pagina-instellingen heeft, zorgt u ervoor dat de
	// instellingen zijn identiek voor het laatste gedeelte van het bestemmingsdocument.
	// Als er nog meer doorlopende secties volgen in het brondocument,
	//dit moet voor die secties worden herhaald.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Doorloop alle secties in het brondocument.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```