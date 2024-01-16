---
title: Kopiera sidhuvuden sidfötter från föregående avsnitt
linktitle: Kopiera sidhuvuden sidfötter från föregående avsnitt
second_title: Aspose.Words Document Processing API
description: Lär dig hur du kopierar sidhuvuden och sidfötter från föregående avsnitt i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du kopierar sidhuvuden och sidfötter från föregående avsnitt i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

 För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från[Aspose.Releases]https://releases.aspose.com/words/net/.

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

Slutligen, spara det ändrade dokumentet:

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

### FAQ's

#### F: Hur kan jag kopiera sidhuvuden och sidfötter från föregående avsnitt till Aspose.Words?

 S: För att kopiera sidhuvuden och sidfötter från föregående avsnitt till Aspose.Words kan du använda`CopyHeadersFootersFromPreviousSection()` metod på strömmen`Section`objekt. Detta kommer att kopiera sidhuvuden och sidfötter från föregående avsnitt till nuvarande avsnitt.

#### F: Är det möjligt att kopiera endast sidhuvud eller sidfot från föregående avsnitt i Aspose.Words?

 S: Ja, det är möjligt att kopiera endast sidhuvudet eller sidfoten från föregående avsnitt i Aspose.Words. För detta kan du använda`CopyHeaderFromPreviousSection()` och`CopyFooterFromPreviousSection()` metoder på strömmen`Section` objekt för att specifikt kopiera sidhuvudet eller sidfoten från föregående avsnitt till det aktuella avsnittet.

#### F: Ersätter kopiering av sidhuvuden och sidfötter från föregående avsnitt befintliga sidhuvuden och sidfötter i det aktuella avsnittet?

S: Ja, kopiering av sidhuvuden och sidfötter från föregående avsnitt ersätter befintliga sidhuvuden och sidfötter i det aktuella avsnittet. Om du vill behålla befintliga sidhuvuden och sidfötter och lägga till dem i de kopierade sidhuvuden och sidfötter, måste du göra ytterligare en operation för att slå samman innehållet.

#### F: Hur kan jag kontrollera om ett avsnitt har ett sidhuvud eller en sidfot från föregående avsnitt i Aspose.Words?

S: För att kontrollera om ett avsnitt har en sidhuvud eller sidfot från föregående avsnitt i Aspose.Words kan du använda`HasHeader` och`HasFooter` fastigheter på`Section` objekt för att avgöra om sidhuvudet eller sidfoten finns. Om`HasHeader` eller`HasFooter` returnerar`false`, betyder det att det inte finns någon sidhuvud eller sidfot från föregående avsnitt i det här avsnittet.