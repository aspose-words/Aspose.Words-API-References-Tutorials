---
title: Efter sektioner
linktitle: Efter sektioner
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du delar upp ett Word-dokument i separata avsnitt med Aspose.Words för .NET med komplett kodexempel.
type: docs
weight: 10
url: /sv/net/split-document/by-sections/
---

I det här exemplet kommer vi att visa dig hur du delar upp ett Word-dokument i separata avsnitt med hjälp av funktionen By Sections i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och få separata dokument för varje avsnitt.

## Steg 1: Ladda dokumentet

Till att börja med måste vi ange katalogen för ditt dokument och ladda dokumentet i ett dokumentobjekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Steg 2: Dela upp dokumentet i sektioner

Nu ska vi iterera igenom varje avsnitt av dokumentet och dela upp dokumentet i mindre delar, avsnitt för avsnitt. Så här gör du:

```csharp
for (int i = 0; i < doc. Sections. Count; i++)
{
// Dela upp dokumentet i mindre delar, i det här fallet separera det efter avsnitt.
Section section = doc.Sections[i].Clone();

Document newDoc = new Document();
newDoc.Sections.Clear();

Section newSection = (Section) newDoc.ImportNode(section, true);
newDoc.Sections.Add(newSection);

// Spara varje avsnitt som ett separat dokument.
newDoc.Save(dataDir + $"SplitDocument.ParSections_{i}.docx");
}
```

### Exempel på källkod för By Sections med Aspose.Words för .NET

Här är den fullständiga källkoden för By Sections-funktionen i Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	for (int i = 0; i < doc.Sections.Count; i++)
	{
		// Dela upp ett dokument i mindre delar, i det här fallet delat efter avsnitt.
		Section section = doc.Sections[i].Clone();

		Document newDoc = new Document();
		newDoc.Sections.Clear();

		Section newSection = (Section) newDoc.ImportNode(section, true);
		newDoc.Sections.Add(newSection);

		// Spara varje avsnitt som ett separat dokument.
		newDoc.Save(dataDir + $"SplitDocument.BySections_{i}.docx");
	}

```

Med denna kod kommer du att kunna dela upp ett Word-dokument i separata sektioner med Aspose.Words för .NET.

Nu kan du enkelt arbeta med specifika avsnitt.

