---
title: Starta om listnummer
linktitle: Starta om listnummer
second_title: Aspose.Words Document Processing API
description: Lär dig hur du återställer numret på en lista i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-list/restart-list-number/
---
I denna steg-för-steg handledning kommer vi att visa dig hur du återställer numret på en lista i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

 För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte redan har gjort det, ladda ner och installera biblioteket från[Aspose.Releases]https://releases.aspose.com/words/net/.

## Steg 1: Skapa dokument- och dokumentgeneratorn

Skapa först ett nytt dokument och en tillhörande dokumentgenerator:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Skapa och anpassa den första listan

Skapa sedan en lista baserad på en befintlig mall och anpassa sedan dess nivåer:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Steg 3: Lägga till objekt till den första listan

Använd dokumentbyggaren för att lägga till objekt till den första listan och ta bort listnummer:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Steg 4: Skapa och anpassa den andra listan

För att återanvända den första listan genom att återställa numret, skapa en kopia av den ursprungliga listlayouten:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Du kan också göra ytterligare ändringar i den andra listan om det behövs.

## Steg 5: Lägga till objekt till den andra listan

Använd dokumentbyggaren igen för att lägga till objekt till den andra listan och ta bort listnumren:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Steg 6: Spara det ändrade dokumentet

Spara slutligen det ändrade dokumentet:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Så ! Du har framgångsrikt återställt numret på en lista i ett Word-dokument med Aspose.Words för .NET.

### Exempel på källkod för återställning av listnummer

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa en lista baserad på en mall.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// För att återanvända den första listan måste vi starta om numreringen genom att skapa en kopia av den ursprungliga listformateringen.
List list2 = doc.Lists.AddCopy(list1);

// Vi kan ändra den nya listan på vilket sätt som helst, inklusive att ställa in ett nytt startnummer.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### FAQ's

#### F: Hur kan jag starta om numreringen av en lista i Aspose.Words?

 S: För att starta om numreringen av en lista i Aspose.Words kan du använda`ListRestartAtNumber` metod för`List` klass. Med den här metoden kan du ställa in ett nytt uppringningsvärde från vilket listan ska startas om. Du kan till exempel använda`list.ListRestartAtNumber(1)` för att starta om numrering från 1.

#### F: Är det möjligt att anpassa prefix och suffix för omstartad listnumrering i Aspose.Words?

 S: Ja, du kan anpassa prefix och suffix för omstartad listnumrering i Aspose.Words. De`ListLevel`klass erbjuder fastigheter som t.ex`ListLevel.NumberPrefix`och`ListLevel.NumberSuffix` som låter dig ange prefix och suffix för varje nivå i listan. Du kan använda dessa egenskaper för att anpassa prefixet och suffixet efter behov.

#### F: Hur kan jag ange ett specifikt numreringsvärde från vilket listan ska startas om?

 S: För att ange ett specifikt nummervärde från vilket listan ska startas om kan du använda`ListRestartAtNumber` metod som skickar det önskade värdet som ett argument. Till exempel, för att starta om numrering från 5, kan du använda`list.ListRestartAtNumber(5)`.

#### F: Är det möjligt att starta om listnumrering på flera nivåer i Aspose.Words?

 S: Ja, Aspose.Words stöder omstartsnumrering av flera listnivåer. Du kan tillämpa`ListRestartAtNumber` metod på varje listnivå för att starta om numreringen individuellt. Du kan till exempel använda`list.Levels[0].ListRestartAtNumber(1)` för att starta om den första listnivån från 1, och`list.Levels[1].ListRestartAtNumber(1)` för att starta om den andra nivålistan med början från 1, och så vidare.



