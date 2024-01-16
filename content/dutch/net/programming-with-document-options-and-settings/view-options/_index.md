---
title: Bekijk Opties
linktitle: Bekijk Opties
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het configureren van documentweergaveopties met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-options-and-settings/view-options/
---

In deze zelfstudie leiden we u door de C#-broncode om weergaveopties te configureren met Aspose.Words voor .NET. Met deze functie kunt u de weergavemodus en het zoomniveau in een document aanpassen.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het Word-document waarvoor we de weergaveopties willen configureren. Gebruik de volgende code om het document te laden:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waar uw document zich bevindt.

## Stap 3: Weergaveopties configureren

Nu gaan we de documentweergaveopties configureren. Gebruik de volgende code om de weergavemodus en het zoomniveau in te stellen:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Deze code stelt de weergavemodus in op "PageLayout" en het zoomniveau op 50%.

### Voorbeeldbroncode voor weergaveopties met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Zorg ervoor dat u het juiste documentpad opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u documentweergaveopties kunt configureren met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u de weergave van uw eigen documenten eenvoudig aanpassen.