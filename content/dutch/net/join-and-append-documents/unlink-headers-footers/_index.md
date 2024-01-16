---
title: Ontkoppel kopteksten en voetteksten
linktitle: Ontkoppel kopteksten en voetteksten
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Word-documenten kunt samenvoegen en toevoegen terwijl u kop- en voetteksten ontkoppelt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/unlink-headers-footers/
---

Deze tutorial begeleidt u bij het gebruik van de functie Unlink Headers Footers van Aspose.Words voor .NET. Met deze functie kunt u Word-documenten samenvoegen en toevoegen terwijl u kop- en voetteksten ontkoppelt van het brondocument.

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

## Stap 3: Ontkoppel kop- en voetteksten in het brondocument

 Om de kop- en voetteksten in het brondocument te ontkoppelen en de kop- en voetteksten van het doeldocument voort te zetten, moet u de`LinkToPrevious` eigendom van de`HeadersFooters` verzameling in de eerste sectie van het brondocument`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Stap 4: Voeg het brondocument toe aan het doeldocument

 Nu kunt u het brondocument aan het doeldocument toevoegen met behulp van de`AppendDocument` werkwijze van de`Document` klas. De`ImportFormatMode.KeepSourceFormatting` parameter zorgt ervoor dat de bronopmaak behouden blijft tijdens de toevoegbewerking.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 5: Sla het definitieve document op

 Sla ten slotte het samengevoegde document op met de functie Ontkoppel kopteksten en voetteksten ingeschakeld met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Voorbeeldbroncode voor Unlink Headers Footers met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie "Unlink Headers Footers" in C# met behulp van Aspose.Words voor .NET:

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Ontkoppel de kop- en voetteksten in het brondocument om dit te stoppen
	// van het voortzetten van de kop- en voetteksten van het doeldocument.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Dat is het! U hebt de functie Unlink Headers Footers met succes geïmplementeerd met Aspose.Words voor .NET. Het uiteindelijke document bevat de samengevoegde inhoud met de kop- en voetteksten van het brondocument, losgekoppeld van het doeldocument.