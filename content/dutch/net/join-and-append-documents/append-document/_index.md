---
title: Document toevoegen
linktitle: Document toevoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de inhoud van het ene document aan het andere kunt toevoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/append-document/
---

In deze zelfstudie wordt uitgelegd hoe u Aspose.Words voor .NET kunt gebruiken om de inhoud van het ene document aan het andere toe te voegen. De meegeleverde broncode laat zien hoe u de bron- en doeldocumenten opent en secties van het brondocument importeert en toevoegt aan het doeldocument.

## Stap 1: Zet het project op

Zorg ervoor dat u aan de volgende vereisten voldoet:

-  Aspose.Words voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van[Aspose.Releases]https://releases.aspose.com/words/net/ of gebruik NuGet-pakketbeheer om het te installeren.
- Een documentmappad waar de bron- en doeldocumenten zich bevinden.

## Stap 2: Open de bron- en doeldocumenten

 Open de bron- en doeldocumenten met behulp van de`Document` klasse constructeur. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Stap 3: Voeg secties uit het brondocument toe aan het doeldocument

 Loop door alle secties in het brondocument en importeer elke sectie in het doeldocument met behulp van de`ImportNode` methode. Voeg vervolgens de geïmporteerde sectie toe aan het doeldocument.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Stap 4: Sla het bestemmingsdocument op

 Sla ten slotte het gewijzigde bestemmingsdocument op met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Hiermee is de implementatie van het toevoegen van een document met Aspose.Words voor .NET voltooid.

### Voorbeeldbroncode voor Append Document met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Loop door alle secties in het brondocument.
	//Sectieknooppunten zijn directe kinderen van het documentknooppunt, dus we kunnen alleen het document opsommen.
	foreach (Section srcSection in srcDoc)
	{
		// Omdat we een sectie van het ene document naar het andere kopiëren,
		// het is vereist om het sectieknooppunt in het bestemmingsdocument te importeren.
		// Hiermee worden eventuele documentspecifieke verwijzingen naar stijlen, lijsten, enz. aangepast.
		//
		// Als u een knooppunt importeert, wordt er een kopie gemaakt van het originele knooppunt, maar de kopie
		// ss klaar om in het bestemmingsdocument te worden ingevoegd.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Nu kan het nieuwe sectieknooppunt aan het doeldocument worden toegevoegd.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```