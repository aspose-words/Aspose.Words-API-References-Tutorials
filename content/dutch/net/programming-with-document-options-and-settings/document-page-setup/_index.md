---
title: Documentpagina-instelling
linktitle: Documentpagina-instelling
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het instellen van een documentlay-out met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-options-and-settings/document-page-setup/
---

In deze zelfstudie leiden we u door de C#-broncode om de documentlay-out te configureren met Aspose.Words voor .NET. Met deze functie kunt u de lay-outmodus, het aantal tekens per regel en het aantal regels per pagina instellen.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het Word-document dat we willen configureren. Gebruik de volgende code om het document te laden:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waar uw document zich bevindt.

## Stap 3: Het opzetten van de lay-out

Laten we nu de documentindeling configureren. Gebruik de volgende code om de lay-outmodus, het aantal tekens per regel en het aantal regels per pagina in te stellen:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Deze code stelt de lay-outmodus in op "Raster" en specificeert vervolgens het aantal tekens per regel en het aantal regels per pagina.

### Voorbeeldbroncode voor documentpagina-instelling met Aspose.Words voor .NET


```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Stel de lay-outmodus in voor een sectie waarmee u het gedrag van het documentraster kunt definiëren.
	// Merk op dat het tabblad Documentraster zichtbaar wordt in het dialoogvenster Pagina-instelling van MS Word.
	// of een Aziatische taal is gedefinieerd als bewerkingstaal.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Zorg ervoor dat u het juiste documentpad opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u de lay-out van een document kunt configureren met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u eenvoudig de lay-out van uw eigen documenten aanpassen.