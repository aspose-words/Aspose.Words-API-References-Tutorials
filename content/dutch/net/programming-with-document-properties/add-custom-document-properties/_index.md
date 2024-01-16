---
title: Aangepaste documenteigenschappen toevoegen
linktitle: Aangepaste documenteigenschappen toevoegen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om aangepaste eigenschappen aan een document toe te voegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-properties/add-custom-document-properties/
---

In deze zelfstudie leiden we u door de C#-broncode om aangepaste eigenschappen toe te voegen aan een document met Aspose.Words voor .NET. Met deze functie kunt u aangepaste informatie aan het document toevoegen.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het Word-document waaraan we aangepaste eigenschappen willen toevoegen. Gebruik de volgende code om het document te laden:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waar uw document zich bevindt.

## Stap 3: Voeg aangepaste eigenschappen toe

Laten we nu aangepaste eigenschappen aan het document toevoegen. Gebruik de volgende code om de eigenschappen toe te voegen:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Deze code controleert eerst of de eigenschap "Authorized" al bestaat in de aangepaste eigenschappen. Als dit bestaat, wordt het proces onderbroken. Anders worden de aangepaste eigenschappen aan het document toegevoegd.

### Voorbeeldbroncode voor het toevoegen van aangepaste documenteigenschappen met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Zorg ervoor dat u het juiste documentpad opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u aangepaste eigenschappen aan een document kunt toevoegen met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u eenvoudig uw eigen aangepaste eigenschappen aan uw documenten toevoegen.