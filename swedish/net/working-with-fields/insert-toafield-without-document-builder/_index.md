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

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

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
