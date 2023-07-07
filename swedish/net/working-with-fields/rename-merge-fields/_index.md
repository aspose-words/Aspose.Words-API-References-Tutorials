---
title: Byt namn på sammanslagningsfält
linktitle: Byt namn på sammanslagningsfält
second_title: Aspose.Words för .NET API Referens
description: I den här handledningen kommer du att lära dig hur du byter namn på sammanslagningsfält i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/rename-merge-fields/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som använder funktionen för att byta namn på sammanslagningsfält i Aspose.Words för .NET. Följ varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa dokumentet och infoga sammanslagningsfälten

Vi börjar med att skapa ett nytt dokument och använda en`DocumentBuilder` för att infoga sammanslagningsfälten.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Steg 3: Byt namn på sammanslagningsfält

Vi går igenom varje fält i dokumentområdet, och om det är ett sammanslagningsfält byter vi namn på fältet genom att lägga till "_Omdöpt" suffix.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Steg 4: Spara dokumentet

 Slutligen kallar vi`Save()` metod för att spara det ändrade dokumentet.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Källkodsexempel för att byta namn på sammanslagningsfält med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa dokumentet och infoga sammanslagningsfälten.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Byt namn på sammanslagningsfält.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Spara dokumentet.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Följ dessa steg för att byta namn på sammanslagningsfält i ditt dokument med Aspose.Words för .NET.

### FAQ's

#### F: Hur kan jag byta namn på sammanslagna fält i ett Word-dokument med Aspose.Words för .NET?

 S: För att byta namn på sammanslagna fält i ett Word-dokument med Aspose.Words för .NET kan du gå igenom fälten i dokumentet med hjälp av`FieldMergingArgs` klass och använd`FieldMergingArgs.FieldName` metod för att byta namn på fält.

#### F: Är det möjligt att bara byta namn på vissa sammanslagna fält i ett Word-dokument med Aspose.Words för .NET?

S: Ja, det är möjligt att bara byta namn på vissa sammanslagna fält i ett Word-dokument med Aspose.Words för .NET. Du kan filtrera vilka fält som ska bytas om med hjälp av specifika kriterier, som fältnamn eller andra relevanta egenskaper. Sedan kan du byta namn på motsvarande fält med hjälp av`FieldMergingArgs.FieldName` metod.

#### F: Hur kan jag kontrollera om ett sammanslaget fält har bytt namn i ett Word-dokument med Aspose.Words för .NET?

 S: För att kontrollera om ett sammanslaget fält har bytt namn i ett Word-dokument med Aspose.Words för .NET, kan du använda`FieldMergedArgs` klass och få tillgång till`FieldMergedArgs.IsMerged` egenskap för att avgöra om fältet döptes om till träff.

#### F: Vilka är konsekvenserna av att byta namn på ett sammanslaget fält i ett Word-dokument med Aspose.Words för .NET?

S: När du byter namn på ett sammanslaget fält i ett Word-dokument med Aspose.Words för .NET ändras namnet på fältet i dokumentet, vilket kan påverka andra funktioner eller processer som beror på fältnamnet. Var noga med att överväga dessa potentiella konsekvenser innan du byter namn på sammanslagna fält.

#### F: Är det möjligt att återställa det ursprungliga namnet på ett sammanslaget fält efter att ha bytt namn på det med Aspose.Words för .NET?

S: Ja, det är möjligt att återställa det ursprungliga namnet på ett sammanfogat fält efter att ha bytt namn på det med Aspose.Words för .NET. Du kan lagra fältets ursprungliga namn i en variabel eller lista och sedan använda den informationen för att återställa det ursprungliga namnet om det behövs.