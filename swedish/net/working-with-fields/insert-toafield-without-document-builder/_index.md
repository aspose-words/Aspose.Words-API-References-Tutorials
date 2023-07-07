---
title: Infoga TOA-fält utan dokumentbyggare
linktitle: Infoga TOA-fält utan dokumentbyggare
second_title: Aspose.Words för .NET API Referens
description: Steg för steg guide för att infoga TOA-fält utan Document Builder med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/insert-toafield-without-document-builder/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "TOA Field Insertion" i Aspose.Words för .NET. Följ varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa dokumentet och stycket

Vi börjar med att skapa ett nytt dokument och initialisera ett stycke.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Steg 3: Infoga TA-fältet

Vi använder klassen FieldTA för att infoga ett TA-fält i stycket.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Steg 4: Lägga till stycket i dokumentets brödtext

Vi lägger till stycket som innehåller TA-fältet i dokumentets brödtext.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Steg 5: Skapa stycket för TOA-fältet

Vi skapar ett nytt stycke för TOA-fältet.

```csharp
para = new Paragraph(doc);
```

## Steg 6: Infoga TOA-fältet

Vi använder klassen FieldToa för att infoga ett TOA-fält i stycket.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Steg 7: Lägga till stycket i dokumentets brödtext

Vi lägger till stycket som innehåller TOA-fältet i dokumentets brödtext.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Steg 8: Uppdatera TOA-fältet

 Slutligen kallar vi`Update()` metod för att uppdatera TOA-fältet.

```csharp
fieldToa.Update();
```

### Källkodsexempel för TOA-fältinfogning utan Document Builder med Aspose.Words för .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Vi vill infoga TA- och TOA-fält så här:
// { TA \c 1 \l "Värde 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### FAQ's

#### F: Hur anpassar man utseendet på TOA-fältet som infogas i Word-dokumentet med Aspose.Words för .NET?

S: Du kan anpassa utseendet på det infogade TOA-fältet genom att använda egenskaperna för`FieldTOA` objekt för att ange formateringsalternativ.

#### F: Kan jag lägga till flera TOA-fält i ett enda Word-dokument med Aspose.Words för .NET?

S: Ja, du kan lägga till flera TOA-fält i ett enda Word-dokument med Aspose.Words för .NET. Upprepa bara infogningsstegen för varje fält.

#### F: Hur kan jag kontrollera om ett TOA-fält har infogats i ett Word-dokument med Aspose.Words för .NET?

S: För att kontrollera om ett TOA-fält har infogats, kan du bläddra i dokumentinnehållet och söka efter TOA-fältinstanser.

#### F: Påverkar formateringen av Word-dokument med Aspose.Words för .NET om du infogar ett TOA-fält utan att använda DocumentBuilder?

S: Att infoga ett TOA-fält utan att använda DocumentBuilder påverkar inte formateringen av Word-dokumentet direkt. Däremot kan formateringsalternativen för TOA-fältet påverka den övergripande formateringen av dokumentet.