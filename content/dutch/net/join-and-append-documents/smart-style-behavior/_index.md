---
title: Slim stijlgedrag
linktitle: Slim stijlgedrag
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u slim stijlgedrag kunt behouden bij het samenvoegen en toevoegen van Word-documenten met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/smart-style-behavior/
---

Deze tutorial begeleidt u bij het gebruik van de Smart Style Behavior-functie van Aspose.Words voor .NET. Met deze functie kunt u Word-documenten samenvoegen en toevoegen terwijl het slimme stijlgedrag behouden blijft.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

1. Aspose.Words voor .NET geïnstalleerd. Je kunt het downloaden van de Aspose-website of installeren via NuGet.
2. Visual Studio of een andere C#-ontwikkelomgeving.

## Stap 1: Initialiseer de documentmappen

 Eerst moet u het pad naar uw documentmap instellen. Wijzig de waarde van de`dataDir` variabele naar het pad waar uw documenten zich bevinden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad de bron- en doeldocumenten

Vervolgens moet u de bron- en doeldocumenten laden met behulp van Aspose.Words`Document` klas. Werk de bestandsnamen bij in het`Document` constructor volgens uw documentnamen.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Stap 3: Voeg een pagina-einde in het doeldocument in

 Om ervoor te zorgen dat de toegevoegde inhoud op een nieuwe pagina in het doeldocument verschijnt, kunt u een pagina-einde invoegen met behulp van a`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Stap 4: Stel slimme stijlgedragsopties in

Om slim stijlgedrag tijdens de toevoegbewerking in te schakelen, moet u een exemplaar van maken`ImportFormatOptions` en stel de`SmartStyleBehavior`eigendom aan`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## Stap 5: Voeg het brondocument toe aan het doeldocument

 Nu kunt u het brondocument aan het doeldocument toevoegen met behulp van de`InsertDocument` werkwijze van de`DocumentBuilder` klas. Gebruik de`ImportFormatMode.UseDestinationStyles` parameter en geef de`ImportFormatOptions` object om slim stijlgedrag te behouden.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Stap 6: Bewaar het definitieve document

 Sla ten slotte het samengevoegde document op met de functie Slim stijlgedrag ingeschakeld met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### Voorbeeldbroncode voor Smart Style Behavior met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie "Smart Style Behavior" in C# met behulp van Aspose.Words voor .NET:
 
```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

Dat is het! U hebt de functie Smart Style Behavior met succes geïmplementeerd met Aspose.Words voor .NET. Het uiteindelijke document bevat de samengevoegde inhoud waarbij het slimme stijlgedrag behouden blijft.