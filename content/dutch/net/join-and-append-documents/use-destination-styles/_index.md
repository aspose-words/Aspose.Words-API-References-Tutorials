---
title: Gebruik bestemmingsstijlen
linktitle: Gebruik bestemmingsstijlen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Word-documenten kunt samenvoegen en toevoegen terwijl u doeldocumentstijlen toepast met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/use-destination-styles/
---

Deze tutorial begeleidt u bij het gebruik van de functie Use Destination Styles van Aspose.Words voor .NET. Met deze functie kunt u Word-documenten samenvoegen en toevoegen terwijl u de stijlen van het doeldocument toepast.

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

## Stap 3: Voeg het brondocument toe met bestemmingsstijlen

 Om het brondocument aan het doeldocument toe te voegen terwijl u de stijlen van het doeldocument toepast, kunt u de`AppendDocument` werkwijze van de`Document` klas met de`ImportFormatMode.UseDestinationStyles` parameter.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Stap 4: Bewaar het definitieve document

 Sla ten slotte het samengevoegde document op met de functie Bestemmingsstijlen gebruiken ingeschakeld met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Voorbeeldbroncode voor gebruik van bestemmingsstijlen met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie "Gebruik bestemmingsstijlen" in C# met Aspose.Words voor .NET:

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Voeg het brondocument toe met behulp van de stijlen van het doeldocument.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

Dat is het! U hebt de functie Bestemmingsstijlen gebruiken met succes geïmplementeerd met Aspose.Words voor .NET. Het uiteindelijke document bevat de samengevoegde inhoud met de stijlen van het doeldocument toegepast.