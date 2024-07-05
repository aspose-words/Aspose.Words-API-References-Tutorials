---
title: Verwijder bronkopteksten en voetteksten
linktitle: Verwijder bronkopteksten en voetteksten
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u kop- en voetteksten verwijdert terwijl u Word-documenten samenvoegt en toevoegt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/remove-source-headers-footers/
---

Deze tutorial begeleidt u bij het gebruik van de functie Remove Source Headers Footers van Aspose.Words voor .NET. Met deze functie kunt u Word-documenten samenvoegen en toevoegen terwijl u kop- en voetteksten uit het brondocument verwijdert.

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

## Stap 3: Verwijder kop- en voetteksten uit brondocumentsecties

 Om de kop- en voetteksten uit elke sectie in het brondocument te verwijderen, kunt u door de secties lopen met behulp van a`foreach` loop en bel de`ClearHeadersFooters` methode.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Stap 4: Schakel de instelling "LinkToPrevious" uit voor HeadersFooters

Zelfs nadat u de kop- en voetteksten uit het brondocument hebt gewist, bestaat de mogelijkheid dat de instelling "LinkToPrevious" voor`HeadersFooters` kan nog ingesteld worden. Om dit gedrag te voorkomen, moet u dit expliciet instellen`false` voor de eerste secties`HeadersFooters` eigendom.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Stap 5: Voeg het brondocument toe aan het doeldocument

 Nu kunt u het brondocument aan het doeldocument toevoegen met behulp van de`AppendDocument` werkwijze van de`Document` klas. De`ImportFormatMode.KeepSourceFormatting` parameter zorgt ervoor dat de bronopmaak behouden blijft tijdens de toevoegbewerking.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 6: Bewaar het definitieve document

 Sla ten slotte het samengevoegde document op met de functie Bronkopteksten voetteksten verwijderen ingeschakeld met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Voorbeeldbroncode voor het verwijderen van voetteksten van bronkoppen met Aspose.Words voor .NET 

Hier is de volledige broncode voor de functie "Remove Source Headers Footers" in C# met behulp van Aspose.Words voor .NET:


```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Verwijder de kop- en voetteksten van elk van de secties in het brondocument.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Zelfs nadat de kop- en voetteksten uit het brondocument zijn verwijderd, blijft de instelling "LinkToPrevious" behouden
	// voor HeadersFooters kunnen nog steeds worden ingesteld. Hierdoor worden de kop- en voetteksten voortgezet vanaf de bestemming
	// document. Dit moet op false worden ingesteld om dit gedrag te voorkomen.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Dat is het! U hebt de functie Voetteksten van bronkopteksten verwijderen met succes geïmplementeerd met Aspose.Words voor .NET. Het uiteindelijke document bevat de samengevoegde inhoud, waarbij de kop- en voetteksten uit het brondocument zijn verwijderd.