---
title: Infoga sammanslagningsfält med DOM
linktitle: Infoga sammanslagningsfält med DOM
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar anpassade sammanslagningsfält i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/insert-merge-field-using-dom/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som använder funktionen "Insert Field Merge Field" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa Document and DocumentBuilder

Vi börjar med att skapa ett nytt dokument och initiera en DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Flytta markören till stycket

 Vi använder`MoveTo()` metoden i DocumentBuilder för att flytta markören till stycket där vi vill infoga fältsammanfogningsfältet.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Steg 4: Infoga fältsammanfogningsfältet

 Vi använder DocumentBuilder's`InsertField()` metod för att infoga ett sammanslagningsfält för fält i stycket.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Vi konfigurerar sedan egenskaperna för fältsammanslagning genom att ange lämpliga alternativ, såsom fältnamn, text före och efter fältet och vertikala formateringsalternativ.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Slutligen kallar vi`Update()` metod för att uppdatera fältet.

```csharp
field. Update();
```

### Exempel på källkod för att infoga ett sammanslagningsfält för fält med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa dokumentet och DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Flytta markören till stycket.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Infoga sammanslagningsfält för fält.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Uppdatera fältet.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

I det här exemplet skapade vi ett nytt dokument, flyttade markören till önskat stycke och infogade sedan ett sammanslagningsfält för fält i dokumentet.

### FAQ's

#### F: Hur kan jag infoga ett sammanslagningsfält i ett Word-dokument med Aspose.Words för .NET med DOM?

S: För att infoga ett sammanslagningsfält i ett Word-dokument med Aspose.Words för .NET med DOM, kan du följa dessa steg:

1. Navigera till stycket där du vill infoga sammanslagningsfältet.
2.  Skapa en`FieldMergeField` objekt.
3. Ställ in egenskaperna för sammanslagningsfältet, såsom fältnamn och formateringsalternativ.
4.  Lägg till sammanslagningsfältet i stycket med hjälp av`Paragraph.AppendChild` metod.

#### F: Hur kan jag ange källdata för sammanslagningsfält i Aspose.Words för .NET?

S: För att ange källdata för sammanslagningsfältet i Aspose.Words för .NET kan du använda`FieldMergeField.FieldName` metod för att ange namnet på sammanslagningsfältet, vilket är namnet på ett fält i en extern datakälla som en CSV-fil, databas, etc. Du kan också använda`FieldMergeField.Text` metod för att ställa in sammanslagningsfältvärdet direkt.

#### F: Kan jag anpassa utseendet på sammanslagningsfältet i ett Word-dokument med Aspose.Words för .NET?

 S: Ja, du kan anpassa utseendet på sammanslagningsfältet i ett Word-dokument med Aspose.Words för .NET. Du kan ställa in formateringsalternativ som skiftläge, teckensnitt, färg, etc. med hjälp av egenskaperna för`FieldMergeField` objekt.

#### F: Hur kan jag kontrollera om ett sammanslagningsfält har infogats i ett Word-dokument med Aspose.Words för .NET?

 S: För att kontrollera om ett sammanslagningsfält har infogats, kan du bläddra i dokumentinnehållet och söka efter sammanslagningsfältsinstanser. Du kan använda metoderna och egenskaperna för`Document` objekt för att komma åt stycken, fält och andra delar av dokumentet.

#### F: Påverkar Word-dokumentstrukturen med Aspose.Words för .NET om du infogar ett sammanfogningsfält med DOM?

S: Att infoga ett sammanfogningsfält med hjälp av DOM påverkar inte strukturen i Word-dokumentet direkt. Det lägger dock till ett nytt fältelement till dokumentinnehållet. Du kan manipulera dokumentstrukturen genom att lägga till, ta bort eller ändra befintliga element enligt dina behov.