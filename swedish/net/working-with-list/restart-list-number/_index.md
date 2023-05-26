---
title: Starta om listnummer
linktitle: Starta om listnummer
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du återställer numret på en lista i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-list/restart-list-number/
---
denna steg-för-steg handledning kommer vi att visa dig hur du återställer numret på en lista i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte redan har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

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

Slutligen, spara det ändrade dokumentet:

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




