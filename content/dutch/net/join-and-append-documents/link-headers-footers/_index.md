---
title: Kopteksten en voetteksten koppelen
linktitle: Kopteksten en voetteksten koppelen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u kop- en voetteksten koppelt terwijl u Word-documenten samenvoegt en toevoegt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/link-headers-footers/
---

Deze tutorial begeleidt u bij het gebruik van de functie Link Headers Footers van Aspose.Words voor .NET. Met deze functie kunt u meerdere Word-documenten samenvoegen en toevoegen, terwijl u de kop- en voetteksten van het brondocument koppelt aan de vorige sectie in het doeldocument.

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

## Stap 3: Stel in dat het toegevoegde document op een nieuwe pagina verschijnt

 Om ervoor te zorgen dat de inhoud van het brondocument op een nieuwe pagina in het doeldocument verschijnt, moet u de`SectionStart` eigenschap van de eerste sectie in het brondocument`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Stap 4: Koppel kop- en voetteksten aan de vorige sectie

 Om de kop- en voetteksten van het brondocument te koppelen aan de vorige sectie in het doeldocument, kunt u de`LinkToPrevious` werkwijze van de`HeadersFooters` verzameling. Door te passeren`true` als parameter overschrijft u eventuele bestaande kop- of voetteksten in het brondocument.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Stap 5: Voeg het brondocument toe aan het doeldocument

 Nu kunt u het brondocument aan het doeldocument toevoegen met behulp van de`AppendDocument` werkwijze van de`Document` klas. De`ImportFormatMode.KeepSourceFormatting` parameter zorgt ervoor dat de bronopmaak behouden blijft tijdens de toevoegbewerking.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 6: Bewaar het definitieve document

 Sla ten slotte het samengevoegde document op met de gekoppelde kop- en voetteksten met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Voorbeeldbroncode voor linkheaders-voetteksten met Aspose.Words voor .NET 

Hier is de volledige broncode voor de functie "Link Headers Footers" in C# met behulp van Aspose.Words voor .NET:


```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Stel in dat het toegevoegde document op een nieuwe pagina verschijnt.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Koppel de kop- en voetteksten in het brondocument aan de vorige sectie.
	// Hiermee worden alle kop- en voetteksten die al in het brondocument voorkomen overschreven.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Dat is het! U hebt de functie Link Headers Footers met succes geïmplementeerd met Aspose.Words voor .NET. Het uiteindelijke document bevat de samengevoegde inhoud met de kop- en voetteksten van het brondocument dat is gekoppeld aan de vorige sectie in het doeldocument.