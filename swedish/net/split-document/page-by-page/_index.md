---
title: Sida för sida
linktitle: Sida för sida
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att förklara C#-källkoden för Aspose.Words Sida för sida-funktionen för .NET
type: docs
weight: 10
url: /sv/net/split-document/page-by-page/
---

I den här handledningen går vi igenom hur du delar upp ett Word-dokument i enskilda sidor med hjälp av funktionen Sida för sida i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och få separata dokument för varje sida.

## Steg 1: Ladda dokumentet

För att komma igång, ange katalogen för ditt dokument och ladda dokumentet i ett dokumentobjekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Steg 2: Dela upp dokumentet för sida

Nu går vi igenom varje sida i dokumentet och delar upp dokumentet i enskilda sidor. Här är hur:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Spara varje sida som ett separat dokument.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

## Steg 3: Slå samman dokument

När du har separata dokument för varje sida kan du slå ihop dem om det behövs. Här är hur:

```csharp
MergeDocuments();
```

### Exempel på källkod för sida för sida med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Sida för sida i Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	int pageCount = doc.PageCount;

	for (int page = 0; page < pageCount; page++)
	{
		// Spara varje sida som ett separat dokument.
		Document extractedPage = doc.ExtractPages(page, 1);
		extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
	}
	

	MergeDocuments();

```

Med denna kod kommer du att kunna dela upp ett Word-dokument i enskilda sidor med Aspose.Words för .NET. Du kan även slå samman separata dokument om det behövs.

