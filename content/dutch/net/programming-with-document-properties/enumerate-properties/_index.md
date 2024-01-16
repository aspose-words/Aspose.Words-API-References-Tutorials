---
title: Eigenschappen opsommen
linktitle: Eigenschappen opsommen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het opsommen van documenteigenschappen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-properties/enumerate-properties/
---

In deze zelfstudie leiden we u door de C#-broncode om documenteigenschappen op te sommen met Aspose.Words voor .NET. Met deze functie hebt u toegang tot ingebouwde en aangepaste eigenschappen van een document.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document laden

In deze stap laden we het Word-document waarvan we de eigenschappen willen vermelden. Gebruik de volgende code om het document te laden:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad van de map waar uw document zich bevindt.

## Stap 3: Eigenschappen opsommen

Laten we nu de documenteigenschappen vermelden, zowel ingebouwde als aangepaste eigenschappen. Gebruik de volgende code:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Deze code geeft de documentnaam weer en vermeldt vervolgens de ingebouwde en aangepaste eigenschappen, waarbij hun naam en waarde worden weergegeven.

### Voorbeeldbroncode voor Enumerate Properties met Aspose.Words voor .NET

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Zorg ervoor dat u het juiste documentpad opgeeft in het`dataDir` variabel.

U hebt nu geleerd hoe u documenteigenschappen kunt opsommen met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u eenvoudig de eigenschappen van uw eigen documenten openen en bekijken.

