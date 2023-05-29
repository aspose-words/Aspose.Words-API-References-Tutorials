---
title: Kopiera sidhuvuden sidfötter från föregående avsnitt
linktitle: Kopiera sidhuvuden sidfötter från föregående avsnitt
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du kopierar sidhuvuden och sidfötter från föregående avsnitt i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du kopierar sidhuvuden och sidfötter från föregående avsnitt i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Åtkomst till föregående avsnitt

 Hämta först föregående avsnitt genom att gå till`PreviousSibling` egenskapen för den aktuella sektionen:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## Steg 2: Sök efter föregående avsnitt

Kontrollera sedan om ett tidigare avsnitt finns. Om det inte finns något tidigare avsnitt returnerar vi helt enkelt:

```csharp
if (previousSection == null)
    return;
```

## Steg 3: Rensa och kopiera sidhuvuden och sidfötter

För att kopiera sidhuvuden och sidfötter från föregående avsnitt till det aktuella avsnittet rensar vi befintliga sidhuvuden och sidfötter i det aktuella avsnittet och går sedan igenom sidhuvuden och sidfötter i föregående avsnitt för att lägga till klonade kopior till det aktuella avsnittet:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## Steg 4: Spara dokumentet

Spara slutligen det ändrade dokumentet:

```csharp
doc.Save("OutputDocument.docx");
```

Det är allt! Du har framgångsrikt kopierat sidhuvuden och sidfötter från föregående avsnitt till det aktuella avsnittet i ett Word-dokument med Aspose.Words för .NET.

### Exempel på källkod för kopiera sidhuvuden sidfötter från föregående avsnitt med Aspose.Words för .NET

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.