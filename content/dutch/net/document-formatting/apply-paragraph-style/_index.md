---
title: Pas alineastijl toe in Word-document
linktitle: Pas alineastijl toe in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een alineastijl toepast in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/document-formatting/apply-paragraph-style/
---
In deze zelfstudie laten we u zien hoe u een alineastijl toepast met Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en de alineastijl toe te passen.

## Stap 1: Het document aanmaken en configureren

Maak om te beginnen een nieuw document en een bijbehorend DocumentBuilder-object. Hier is hoe:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Configureren van de alineastijl

We zullen nu de alineastijl configureren met behulp van de ingebouwde stijlidentificatie. Hier is hoe:

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
```

## Stap 3: Voeg inhoud toe

We gaan inhoud aan de paragraaf toevoegen. Hier is hoe:

```csharp
builder.Write("Hello");
doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
```

### Voorbeeldbroncode voor het toepassen van alineastijl met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie Paragraafstijl toepassen met Aspose.Words voor .NET:

```csharp

	// Het pad naar de documentenmap.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Title;
	builder.Write("Hello");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyParagraphStyle.docx");
	
```

Met deze code kunt u een alineastijl toepassen met Aspose.Words voor .NET.

## Conclusie

 In deze zelfstudie hebben we onderzocht hoe u een alineastijl in een Word-document kunt toepassen met Aspose.Words voor .NET. Door het instellen van de`StyleIdentifier` eigendom van de`ParagraphFormat`konden we een ingebouwde stijl op de alinea toepassen. Aspose.Words voor .NET biedt een breed scala aan opmaakopties, waaronder de mogelijkheid om aangepaste stijlen te maken en toe te passen, zodat u gemakkelijk professioneel ogende documenten kunt maken.

### Veelgestelde vragen

#### Vraag: Hoe pas ik een alineastijl toe in een Word-document met Aspose.Words voor .NET?

A: Volg deze stappen om een alineastijl toe te passen in een Word-document met Aspose.Words voor .NET:
1.  Maak een nieuw document en a`DocumentBuilder` voorwerp.
2.  Configureer de alineastijl door de`StyleIdentifier` eigendom van de`ParagraphFormat` naar de gewenste stijlidentificatie (bijv.`StyleIdentifier.Title`, `StyleIdentifier.Heading1`, enz.).
3.  Voeg inhoud toe aan de alinea met behulp van de`Write` werkwijze van de`DocumentBuilder`.
4.  Sla het document op met behulp van de`Save` methode.

#### Vraag: Wat zijn stijl-ID's in Aspose.Words voor .NET?

 A: Stijl-ID's in Aspose.Words voor .NET zijn vooraf gedefinieerde constanten die ingebouwde alineastijlen vertegenwoordigen. Elke stijlidentificatie komt overeen met een specifieke stijl, zoals 'Titel', 'Kop1', 'Kop2', enz. Door de`StyleIdentifier` eigendom van de`ParagraphFormat`, kunt u de bijbehorende stijl op de alinea toepassen.

#### Vraag: Kan ik aangepaste alineastijlen maken en toepassen met Aspose.Words voor .NET?

A: Ja, met Aspose.Words voor .NET kunt u aangepaste alineastijlen maken en toepassen. U kunt uw eigen stijlen definiëren met specifieke opmaakeigenschappen, zoals lettertype, uitlijning, inspringing, enz., en deze toepassen op alinea's in uw document. Hierdoor kunt u een consistente en aangepaste opmaak in uw hele document realiseren.