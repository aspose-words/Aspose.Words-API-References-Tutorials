---
title: Byt ut text i tabell
linktitle: Byt ut text i tabell
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ersätter text i en tabell i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/replace-text-in-table/
---

I den här artikeln kommer vi att utforska ovanstående C#-källkod för att förstå hur man använder funktionen Ersätt text i tabell i Aspose.Words för .NET-biblioteket. Med den här funktionen kan du hitta och ersätta specifik text i en tabell i ett Word-dokument.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Ladda dokumentet

 Innan vi börjar använda textersättning i en tabell måste vi ladda dokumentet i Aspose.Words för .NET. Detta kan göras med hjälp av`Document` klass och ange sökvägen till dokumentfilen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

## Steg 2: Gå till brädet

 När dokumentet har laddats måste vi navigera till tabellen där vi vill utföra textersättningen. I vårt exempel använder vi`GetChild` metod med`NodeType.Table` parameter för att få den första tabellen i dokumentet:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Steg 3: Utför textersättning

 Nu använder vi`Range.Replace` metod för att utföra textersättningen i arrayen. I vårt exempel ersätter vi alla förekomster av ordet "morötter" med "ägg" med hjälp av`FindReplaceOptions` alternativet med`FindReplaceDirection.Forward` sökriktning. Dessutom ersätter vi värdet "50" med "20" i den sista cellen i den sista raden i tabellen:

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Steg 4: Spara det redigerade dokumentet

 Slutligen sparar vi det ändrade dokumentet i en specificerad katalog med hjälp av`Save` metod:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
```

Aspose.Words för .NET Vi följde en steg-för-steg-guide för att ladda ett dokument, komma åt tabellen, utföra textersättningen och spara det ändrade dokumentet.

### Exempel på källkod för Ersätt text i tabell med Aspose.Words för .NET

Här är den fullständiga källkoden för att demonstrera hur du använder textersättning i en tabell med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Tables.docx");

	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
	table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
    
```

## Slutsats

den här artikeln utforskade vi C#-källkoden för att förstå hur man använder Asposes Ersätt text i tabell-funktion.
