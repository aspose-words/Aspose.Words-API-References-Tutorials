---
title: Pagina-indeling bijwerken
linktitle: Pagina-indeling bijwerken
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de pagina-indeling kunt bijwerken wanneer u Word-documenten samenvoegt en toevoegt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/update-page-layout/
---

Deze tutorial begeleidt u bij het gebruik van de functie Update Page Layout van Aspose.Words voor .NET. Deze functie zorgt ervoor dat de pagina-indeling correct wordt bijgewerkt bij het samenvoegen en toevoegen van Word-documenten.

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

## Stap 3: Update de pagina-indeling voor het doeldocument

 Om ervoor te zorgen dat de pagina-indeling correct wordt bijgewerkt voordat u het brondocument toevoegt, kunt u de`UpdatePageLayout` methode op het bestemmingsdocument.

```csharp
dstDoc.UpdatePageLayout();
```

## Stap 4: Voeg het brondocument toe aan het doeldocument

 Nu kunt u het brondocument aan het doeldocument toevoegen met behulp van de`AppendDocument` werkwijze van de`Document` klas. De`ImportFormatMode.KeepSourceFormatting` parameter zorgt ervoor dat de bronopmaak behouden blijft tijdens de toevoegbewerking.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 5: Werk de pagina-indeling opnieuw bij

 Nadat u het brondocument hebt toegevoegd, moet u het`UpdatePageLayout`methode opnieuw toe te passen op het doeldocument om ervoor te zorgen dat eventuele wijzigingen die na de toevoegbewerking zijn aangebracht, worden weerspiegeld in de weergegeven uitvoer.

```csharp
dstDoc.UpdatePageLayout();
```

## Stap 6: Bewaar het definitieve document

 Sla ten slotte het samengevoegde document op met de functie Pagina-indeling bijwerken ingeschakeld met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Voorbeeldbroncode voor het bijwerken van de pagina-indeling met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie "Update Page Layout" in C# met Aspose.Words voor .NET:

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Als het doeldocument wordt weergegeven als PDF, afbeelding enz.
	// of UpdatePageLayout wordt aangeroepen vóór het brondocument. wordt toegevoegd,
	// Alle wijzigingen die daarna worden aangebracht, worden dan niet weerspiegeld in de weergegeven uitvoer
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Om de wijzigingen te kunnen bijwerken naar de weergegeven uitvoer, moet UpdatePageLayout opnieuw worden aangeroepen.
	// Als het niet opnieuw wordt aangeroepen, zal het toegevoegde document niet verschijnen in de uitvoer van de volgende weergave.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Dat is het! U hebt de functie Pagina-indeling bijwerken met succes geïmplementeerd met Aspose.Words voor .NET. Het uiteindelijke document bevat de samengevoegde inhoud, waarbij de pagina-indeling correct is bijgewerkt.