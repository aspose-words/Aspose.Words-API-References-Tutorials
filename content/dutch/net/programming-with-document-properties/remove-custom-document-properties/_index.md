---
title: Aangepaste documenteigenschappen verwijderen
linktitle: Aangepaste documenteigenschappen verwijderen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om aangepaste eigenschappen uit een document te verwijderen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-properties/remove-custom-document-properties/
---

In deze zelfstudie leiden we u door de C#-broncode om aangepaste eigenschappen uit een document te verwijderen met Aspose.Words voor .NET. Met deze functie kunt u een specifieke aangepaste eigenschap uit een document verwijderen.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het Word-document waaruit we de aangepaste eigenschappen willen verwijderen. Gebruik de volgende code om het document te laden:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waar uw document zich bevindt.

## Stap 3: Aangepaste eigenschappen verwijderen

Laten we nu een specifieke aangepaste eigenschap uit het document verwijderen. Gebruik de volgende code:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Met deze code wordt de aangepaste eigenschap 'Geautoriseerde datum' uit het document verwijderd. U kunt 'Geautoriseerde datum' vervangen door de naam van de aangepaste eigenschap die u wilt verwijderen.

### Voorbeeldbroncode voor het verwijderen van aangepaste documenteigenschappen met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Zorg ervoor dat u het juiste documentpad opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u aangepaste eigenschappen uit een document kunt verwijderen met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u eenvoudig aangepaste eigenschappen uit uw eigen documenten verwijderen.