---
title: Start de paginanummering opnieuw
linktitle: Start de paginanummering opnieuw
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de paginanummering opnieuw kunt starten terwijl u Word-documenten samenvoegt en toevoegt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/restart-page-numbering/
---

Deze tutorial begeleidt u bij het gebruik van de functie Paginanummering opnieuw starten van Aspose.Words voor .NET. Met deze functie kunt u Word-documenten samenvoegen en toevoegen terwijl u de paginanummering in het brondocument opnieuw start.

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

## Stap 3: Stel het brondocument in om de paginanummering opnieuw te starten

 Om de paginanummering in het brondocument opnieuw te starten, moet u de`SectionStart` eigenschap van de eerste sectie in het brondocument`SectionStart.NewPage` en stel de`RestartPageNumbering`eigendom aan`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Stap 4: Voeg het brondocument toe aan het doeldocument

 Nu kunt u het brondocument aan het doeldocument toevoegen met behulp van de`AppendDocument` werkwijze van de`Document` klas. De`ImportFormatMode.KeepSourceFormatting` parameter zorgt ervoor dat de bronopmaak behouden blijft tijdens de toevoegbewerking.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Stap 5: Sla het definitieve document op

 Sla ten slotte het samengevoegde document op met de functie Paginanummering opnieuw starten ingeschakeld met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Voorbeeldbroncode voor het opnieuw starten van paginanummering met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie "Paginanummering opnieuw starten" in C# met behulp van Aspose.Words voor .NET:
 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

Dat is het! U hebt de functie Paginanummering opnieuw starten met succes geïmplementeerd met Aspose.Words voor .NET. Het uiteindelijke document bevat de samengevoegde inhoud, waarbij de paginanummering opnieuw wordt gestart in het brondocument.