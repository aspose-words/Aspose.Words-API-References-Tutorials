---
title: Lista Använd destinationsstilar
linktitle: Lista Använd destinationsstilar
second_title: Aspose.Words Document Processing API
description: Lär dig hur du går med i och lägger till Word-dokument samtidigt som du bevarar måldokumentets liststilar med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/list-use-destination-styles/
---

Denna handledning guidar dig genom processen att använda funktionen Listanvändning av destinationsstilar i Aspose.Words för .NET. Med den här funktionen kan du ansluta och lägga till Word-dokument samtidigt som du använder liststilarna för måldokumentet.

## Förutsättningar

Innan du börjar, se till att du har följande:

1. Aspose.Words för .NET installerat. Du kan ladda ner den från Asposes webbplats eller installera den via NuGet.
2. Visual Studio eller någon annan C#-utvecklingsmiljö.

## Steg 1: Initiera dokumentkatalogerna

 Först måste du ställa in sökvägen till din dokumentkatalog. Ändra värdet på`dataDir`variabel till sökvägen där dina dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda käll- och måldokumenten

 Därefter måste du ladda käll- och måldokumenten med hjälp av Aspose.Words`Document` klass. Uppdatera filnamnen i`Document` konstruktör enligt dina dokumentnamn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Steg 3: Ställ in källdokumentet på att fortsätta efter måldokumentet

 För att säkerställa att innehållet från källdokumentet fortsätter efter slutet av måldokumentet måste du ställa in`SectionStart` egenskapen för det första avsnittet i källdokumentet till`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Steg 4: Hantera listformatering

För att hantera listformatering går du igenom varje stycke i källdokumentet och kontrollerar om det är ett listobjekt. Om så är fallet kommer du att jämföra list-ID:t med de befintliga listorna i måldokumentet. Om det finns en lista med samma ID kommer du att skapa en kopia av listan i källdokumentet och uppdatera styckets listformat för att använda den kopierade listan.

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

## Steg 5: Bifoga källdokumentet till destinationsdokumentet

 Nu kan du lägga till källdokumentet till måldokumentet med hjälp av`AppendDocument` metod för`Document` klass. De`ImportFormatMode.UseDestinationStyles` parametern säkerställer att måldokumentets liststilar används under tilläggsoperationen.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Steg 6: Spara det slutliga dokumentet

 Spara slutligen det sammanslagna dokumentet med funktionen Listanvänd destinationsstilar aktiverad med hjälp av`Save` metod för`Document` klass.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Exempel på källkod för List Use Destination Styles med Aspose.Words för .NET 

Här är den fullständiga källkoden för funktionen "List Use Destination Styles" i C# med Aspose.Words för .NET:


```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//Ställ in källdokumentet att fortsätta direkt efter slutet av måldokumentet.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Håll koll på listorna som skapas.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Kontrollera om måldokumentet redan innehåller en lista med detta ID. Om det gör det, så kan detta
			//få de två listorna att köras tillsammans. Skapa istället en kopia av listan i källdokumentet.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// En nyligen kopierad lista finns redan för detta ID, hämta den lagrade listan,
				// och använd den på det aktuella stycket.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Lägg till en kopia av den här listan i dokumentet och spara den för senare referens.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Ställ in listan för detta stycke till den kopierade listan.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Lägg till källdokumentet i slutet av måldokumentet.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Det är allt! Du har framgångsrikt implementerat funktionen Listanvänd destinationsstilar med Aspose.Words för .NET. Det slutliga dokumentet kommer att innehålla det sammanslagna innehållet med liststilarna från måldokumentet.