---
title: Infoga avancerat fält utan dokumentbyggare
linktitle: Infoga avancerat fält utan dokumentbyggare
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar ett avancerat fält i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Advanced Field Insertion without DocumentBuilder" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa dokumentet och stycket

Vi börjar med att skapa ett nytt dokument och hämta första stycket.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Steg 3: Infoga det avancerade fältet

 Vi använder`AppendField()` metod för att infoga ett avancerat fält i stycket.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

Vi konfigurerar sedan de olika egenskaperna för det avancerade fältet genom att ange önskade värden.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 Slutligen kallar vi`Update()` metod för att uppdatera fältet.

```csharp
field. Update();
```

### Exempel på källkoden för att infoga ett avancerat fält utan DocumentBuilder med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapande av dokument.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Infoga det avancerade fältet.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

det här exemplet skapade vi ett nytt dokument, infogade ett avancerat fält utan att använda DocumentBuilder, konfigurerade de olika fältegenskaperna och sparade dokumentet med ett angivet filnamn.

Detta avslutar vår guide om hur man använder funktionen "Infoga avancerat fält utan DocumentBuilder" med Aspose.Words för .NET.

### FAQ's

#### F: Vad är ett avancerat fält i Aspose.Words?

S: Ett avancerat fält i Aspose.Words är en speciell typ av fält som låter dig utföra beräkningar, inkludera villkor och utföra komplexa operationer i ett Word-dokument. Det erbjuder stor flexibilitet för att skapa dynamiska och anpassade fält.

#### F: Hur infogar man ett avancerat fält i ett Word-dokument utan att använda Document Builder i Aspose.Words?

S: För att infoga ett avancerat fält i ett Word-dokument utan att använda Document Builder i Aspose.Words kan du följa dessa steg:

1. Importera dokument och fältklass från namnområdet Aspose.Words.Fields.
2. Skapa en instans av dokument genom att ladda ditt befintliga dokument.
3. Använd metoden InsertField för att infoga ett avancerat fält genom att ange den avancerade fältkoden.
4. Spara dokumentet.

#### F: Hur får man resultatet av ett avancerat fält i ett Word-dokument?

S: För att få resultatet av ett avancerat fält i ett Word-dokument kan du använda egenskapen Result som är tillgänglig i klassen Field. Den här egenskapen returnerar det beräknade resultatet av fältet.

#### F: Kan jag ändra formeln för ett avancerat fält efter att ha infogat det i ett Word-dokument?

S: Ja, du kan redigera formeln för ett avancerat fält efter att ha infogat det i ett Word-dokument. Du kan göra detta genom att komma åt FieldCode-egenskapen för Field-klassen och uppdatera formeln genom att ändra formeltexten.