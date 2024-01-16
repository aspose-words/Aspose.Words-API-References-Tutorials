---
title: Eenvoudig document toevoegen
linktitle: Eenvoudig document toevoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Word-documenten met behouden opmaak kunt samenvoegen en toevoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/simple-append-document/
---

Deze tutorial begeleidt u bij het gebruik van de Simple Append Document-functie van Aspose.Words voor .NET. Met deze functie kunt u Word-documenten samenvoegen en toevoegen zonder extra opties.

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

## Stap 3: Voeg het brondocument toe aan het doeldocument

 Nu kunt u het brondocument aan het doeldocument toevoegen met behulp van de`AppendDocument` werkwijze van de`Document` klas. De`ImportFormatMode.KeepSourceFormatting` parameter zorgt ervoor dat de bronopmaak behouden blijft tijdens de toevoegbewerking.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 4: Bewaar het definitieve document

 Sla ten slotte het samengevoegde document op met de functie Eenvoudig document toevoegen met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Voorbeeldbroncode voor Simple Append Document met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie "Simple Append Document" in C# met behulp van Aspose.Words voor .NET:

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Voeg het brondocument toe aan het doeldocument zonder extra opties.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

Dat is het! U hebt de functie Simple Append Document met succes geïmplementeerd met Aspose.Words voor .NET. Het uiteindelijke document bevat de samengevoegde inhoud waarbij de bronopmaak behouden blijft.