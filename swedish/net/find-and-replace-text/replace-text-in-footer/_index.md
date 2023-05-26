---
title: Ersätt text i sidfot
linktitle: Ersätt text i sidfot
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ersätter text i sidfoten i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/replace-text-in-footer/
---

I den här artikeln kommer vi att utforska ovanstående C#-källkod för att förstå hur man använder funktionen Ersätt text i sidfot i Aspose.Words för .NET-biblioteket. Med den här funktionen kan du hitta och ersätta specifik text i sidfötter i Word-dokument.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Ladda dokumentet

Innan vi börjar använda textersättning i sidfoten måste vi ladda dokumentet i Aspose.Words för .NET. Detta kan göras med hjälp av`Document` klass och ange sökvägen till dokumentfilen:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Footer.docx");
```

## Steg 2: Öppna sidfoten

 När dokumentet har laddats måste vi komma åt sidfoten för att utföra textersättningen. I vårt exempel använder vi`HeadersFooters` egenskapen för den första delen av dokumentet för att få samlingen av sidhuvuden/sidfötter. Därefter väljer vi huvudsidfoten med hjälp av`HeaderFooterType.FooterPrimary` index:

```csharp
HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];
```

## Steg 3: Konfigurera sök- och ersättalternativ

 Nu kommer vi att konfigurera hitta och ersätta alternativ med hjälp av en`FindReplaceOptions` objekt. I vårt exempel sätter vi`MatchCase` till`false` att ignorera skiftläge när du söker, och`FindWholeWordsOnly` till`false` för att låta delar av ord sökas och ersättas:

```csharp
FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };
```

## Steg 4: Ersätt text i sidfoten

 Vi använder`Range.Replace` metod för att utföra textersättning i sidfoten. I vårt exempel ersätter vi frasen "(C) 2006 Aspose Pty Ltd." av "Copyright (C) 2020 av Aspose Pty Ltd." :

```csharp
footer

.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);
```

## Steg 5: Spara det redigerade dokumentet

 Slutligen sparar vi det ändrade dokumentet i en specificerad katalog med hjälp av`Save` metod:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
```

### Exempel på källkod för Ersätt text i sidfot med Aspose.Words för .NET

Här är den fullständiga källkoden för att demonstrera användningen av sidfotsersättning med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Footer.docx");

	HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
	HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

	FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };

	footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
            
        
```

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Ersätt text i sidfot i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att ladda ett dokument, komma åt sidfoten, konfigurera sök- och ersättalternativ, utföra textersättning och spara det redigerade dokumentet.
