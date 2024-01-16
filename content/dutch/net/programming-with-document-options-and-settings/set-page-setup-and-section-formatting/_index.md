---
title: Stel de pagina-instelling en sectieopmaak in
linktitle: Stel de pagina-instelling en sectieopmaak in
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het instellen van de lay-out en sectieopmaak van een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

In deze zelfstudie leiden we u door de C#-broncode om de lay-out en sectieopmaak in te stellen met Aspose.Words voor .NET. Met deze functie kunt u de paginarichting, marges en papierformaat instellen.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document aanmaken

In deze stap gaan we een nieuw document maken. Gebruik de volgende code om het document te maken en de constructor te initialiseren:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waarin u het document wilt opslaan.

## Stap 3: De lay-out instellen en het document opslaan

Laten we nu de documentindeling configureren. Gebruik de volgende code om de richting, marges en papierformaat in te stellen:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Deze code stelt de paginarichting in op liggend, de linkermarge op 50 en het papierformaat op 10x14.

### Voorbeeldbroncode voor het instellen van pagina-instellingen en sectieopmaak met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

Zorg ervoor dat u het juiste pad opgeeft naar de map waarin u het document wilt opslaan`dataDir` variabel.

U hebt nu geleerd hoe u de lay-out en sectieopmaak van een document kunt configureren met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u eenvoudig de lay-out en opmaak van uw eigen documenten aanpassen.