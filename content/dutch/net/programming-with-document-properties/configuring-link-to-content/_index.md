---
title: Koppeling naar inhoud configureren
linktitle: Koppeling naar inhoud configureren
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het instellen van koppelingen naar inhoud in een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-document-properties/configuring-link-to-content/
---

In deze zelfstudie leiden we u door de C#-broncode om koppelingen naar inhoud met Aspose.Words voor .NET in te stellen. Met deze functie kunt u koppelingen maken naar specifieke inhoud in een document.

## Stap 1: Projectconfiguratie

Maak om te beginnen een nieuw C#-project in uw favoriete IDE. Zorg ervoor dat er in uw project naar de Aspose.Words voor .NET-bibliotheek wordt verwezen.

## Stap 2: Het document en de constructor maken

In deze stap maken we een nieuw document en initialiseren we de constructor. Gebruik de volgende code:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Maak een bladwijzer

Nu gaan we een bladwijzer in het document maken. Gebruik de volgende code om een bladwijzer met tekst erin te maken:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Deze code maakt een bladwijzer aan met de naam "MyBookmark" en voegt daar wat tekst aan toe.

## Stap 4: De inhoudslink instellen

Nu zullen we de link naar de inhoud configureren met behulp van de documenteigenschappen. Gebruik de volgende code om de link naar de inhoud toe te voegen en op te halen:

```csharp
// Haal de lijst met alle aangepaste eigenschappen in het document op.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Voeg een inhoudgebonden eigenschap toe.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Deze code voegt een inhoudgerelateerde eigenschap toe met de naam "Bookmark" met de bladwijzer "MyBookmark". Vervolgens haalt het inhoudgerelateerde eigenschapsinformatie op, zoals de linkstatus, de linkbron en de eigenschapswaarde.

### Voorbeeldbroncode voor het configureren van koppelingen naar inhoud met Aspose.Words voor .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Haal een lijst met alle aangepaste documenteigenschappen op uit het bestand.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Voeg gekoppeld aan inhoudseigenschap toe.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

U hebt nu geleerd hoe u de koppeling naar inhoud in een document kunt configureren met Aspose.Words voor .NET. Door de stapsgewijze handleiding in deze zelfstudie te volgen, kunt u eenvoudig koppelingen naar specifieke inhoud in uw eigen documenten maken en configureren.