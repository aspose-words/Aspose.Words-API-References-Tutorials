---
title: Lijst Behoud bronopmaak
linktitle: Lijst Behoud bronopmaak
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de lijstopmaak kunt behouden terwijl u Word-documenten samenvoegt en toevoegt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/list-keep-source-formatting/
---

Deze tutorial begeleidt u bij het gebruik van de functie List Keep Source Formatting van Aspose.Words voor .NET. Met deze functie kunt u Word-documenten samenvoegen en toevoegen, terwijl de bronopmaak van lijsten behouden blijft.

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

Vervolgens moet u de bron- en doeldocumenten laden met behulp van Aspose.Words.`Document` klas. Werk de bestandsnamen bij in het`Document` constructor volgens uw documentnamen.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Stap 3: Stel het brondocument in op continu stromen

 Om ervoor te zorgen dat de inhoud van het brondocument continu doorstroomt wanneer deze aan het doeldocument wordt toegevoegd, moet u de`SectionStart` eigenschap van de eerste sectie in het brondocument`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Stap 4: Voeg het brondocument toe aan het doeldocument

 Nu kunt u het brondocument aan het doeldocument toevoegen met behulp van de`AppendDocument` werkwijze van de`Document` klas. De`ImportFormatMode.KeepSourceFormatting`parameter zorgt ervoor dat de bronopmaak, inclusief de opmaak van lijsten, behouden blijft tijdens de toevoegbewerking.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 5: Sla het definitieve document op

 Sla ten slotte het samengevoegde document op met de functie Lijst behouden bronopmaak ingeschakeld met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### Voorbeeldbroncode voor List Keep Source Formatting met Aspose.Words voor .NET 

Hier is de volledige broncode voor de functie List Keep Source Formatting in C# met behulp van Aspose.Words voor .NET:

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Voeg de inhoud van het document toe, zodat deze continu doorstroomt.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

Dat is het! U hebt de functie List Keep Source Formatting met succes geïmplementeerd met Aspose.Words voor .NET. Het uiteindelijke document zal de samengevoegde inhoud bevatten, waarbij de lijstopmaak van het brondocument behouden blijft.