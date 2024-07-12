---
title: Infoga författarefält
linktitle: Infoga författarefält
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar ett AUTHOR-fält i dina Word-dokument med Aspose.Words för .NET. Ange författarens namn för att anpassa dina dokument.
type: docs
weight: 10
url: /sv/net/working-with-fields/insert-author-field/
---


Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Infoga ett AUTHOR-fält" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa dokumentet och stycket

Vi börjar med att skapa ett nytt dokument och hämta första stycket.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Steg 3: Infoga AUTHOR-fältet

 Vi använder`AppendField()` metod för att infoga ett AUTHOR-fält i stycket.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Vi konfigurerar sedan fältets`AuthorName` egenskap för att ange författarens namn.

```csharp
field. AuthorName = "Test1";
```

 Slutligen kallar vi`Update()` metod för att uppdatera fältet.

```csharp
field. Update();
```

### Exempel på källkoden för att infoga ett AUTHOR-fält med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapande av dokument.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Infoga AUTHOR-fältet.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

I det här exemplet skapade vi ett nytt dokument, infogade ett AUTHOR-fält, konfigurerade författarens namn och sparade dokumentet med ett specificerat filnamn.

Detta avslutar vår guide om hur du använder funktionen "Infoga AUTHOR Field" med Aspose.Words för .NET.

### FAQ's

#### F: Vad är ett författarfält i Aspose.Words?

S: Ett författarefält i Aspose.Words är ett specialfält som automatiskt infogar och uppdaterar författarens namn i ett Word-dokument. Det används ofta för att ange vem som skapade eller modifierade dokumentet.

#### F: Hur uppdaterar man författarefältet i ett Word-dokument med Aspose.Words?

S: Författarfältet i ett Word-dokument kan uppdateras för att återspegla den aktuella författarens namn. För detta kan du använda metoden UpdateFields som är tillgänglig i klassen Document. Denna metod kommer att uppdatera alla fält i dokumentet, inklusive författarefältet.

#### F: Är det möjligt att anpassa formatet för författarefältet i ett Word-dokument?

S: Ja, det är möjligt att anpassa formatet för författarefältet i ett Word-dokument. Som standard visar författarens fält helt enkelt författarens namn. Du kan dock lägga till ytterligare information såsom datum och tid för ändring med hjälp av formateringsalternativen som finns i Aspose.Words.

#### F: Är författarens fält känsligt för efterföljande ändringar av författarens namn?

S: Ja, författarens fält är känsligt för efterföljande ändringar av författarens namn. Om du ändrar författarnamnet i dokumentegenskaperna kommer författarfältet automatiskt att uppdateras med det nya namnet vid uppdatering av dokumentfält.