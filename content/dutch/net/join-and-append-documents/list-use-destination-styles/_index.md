---
title: Lijst Gebruik bestemmingsstijlen
linktitle: Lijst Gebruik bestemmingsstijlen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Word-documenten kunt samenvoegen en toevoegen terwijl u de lijststijlen van het doeldocument behoudt met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/join-and-append-documents/list-use-destination-styles/
---

Deze tutorial begeleidt u bij het gebruik van de functie List Use Destination Styles van Aspose.Words voor .NET. Met deze functie kunt u Word-documenten samenvoegen en toevoegen terwijl u de lijststijlen van het doeldocument gebruikt.

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Stap 3: Stel het brondocument in op Doorgaan na het doeldocument

 Om ervoor te zorgen dat de inhoud van het brondocument doorgaat na het einde van het doeldocument, moet u de`SectionStart` eigenschap van de eerste sectie in het brondocument`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Stap 4: Lijstopmaak afhandelen

Om de lijstopmaak af te handelen, herhaalt u elke alinea in het brondocument en controleert u of het een lijstitem is. Als dit het geval is, vergelijkt u de lijst-ID met de bestaande lijsten in het bestemmingsdocument. Als er een lijst met dezelfde ID bestaat, maakt u een kopie van de lijst in het brondocument en werkt u de lijstindeling van de alinea bij om de gekopieerde lijst te gebruiken.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Stap 5: Voeg het brondocument toe aan het doeldocument

 Nu kunt u het brondocument aan het doeldocument toevoegen met behulp van de`AppendDocument` werkwijze van de`Document` klas. De`ImportFormatMode.UseDestinationStyles` parameter zorgt ervoor dat de lijststijlen van het doeldocument worden gebruikt tijdens de toevoegbewerking.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Stap 6: Bewaar het definitieve document

Sla ten slotte het samengevoegde document op met de functie Lijstgebruik bestemmingsstijlen ingeschakeld met behulp van de`Save` werkwijze van de`Document` klas.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Voorbeeldbroncode voor Lijst Gebruik bestemmingsstijlen met Aspose.Words voor .NET 

Hier is de volledige broncode voor de functie "List Use Destination Styles" in C# met behulp van Aspose.Words voor .NET:


```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Stel het brondocument zo in dat het direct na het einde van het bestemmingsdocument verdergaat.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Houd de lijsten bij die worden aangemaakt.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Controleer of het bestemmingsdocument al een lijst met dit ID bevat. Als dat zo is, dan mag dit
			// ervoor zorgen dat de twee lijsten samen worden uitgevoerd. Maak in plaats daarvan een kopie van de lijst in het brondocument.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Er bestaat al een nieuw gekopieerde lijst voor deze ID, haal de opgeslagen lijst op,
				// en gebruik het voor de huidige paragraaf.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Voeg een kopie van deze lijst toe aan het document en bewaar deze voor later gebruik.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Stel de lijst van deze paragraaf in op de gekopieerde lijst.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Voeg het brondocument toe aan het einde van het doeldocument.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Dat is het! U hebt de functie Lijstgebruikbestemmingsstijlen met succes geïmplementeerd met Aspose.Words voor .NET. Het uiteindelijke document bevat de samengevoegde inhoud met de lijststijlen uit het doeldocument.