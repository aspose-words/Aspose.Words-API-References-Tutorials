---
title: Ändra språk
linktitle: Ändra språk
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ändrar språk för datum- och nummerformatering i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/change-locale/
---

I den här handledningen kommer vi att guida dig genom processen att ändra språket i Word-dokument med Aspose.Words för .NET. Genom att ändra språket kan du styra formateringen av datum och siffror under kopplingsoperationer. Vi kommer att förse dig med den nödvändiga C#-källkoden och steg-för-steg-instruktioner för att uppnå detta.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa en Document and DocumentBuilder
För att börja skapa en instans av klassen Document och ett DocumentBuilder-objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Infoga ett fält
Infoga sedan ett sammanfogningsfält i dokumentet med metoden InsertField:

```csharp
builder.InsertField("MERGEFIELD Date");
```

I ovanstående kod infogar vi ett sammanslagningsfält med namnet "Datum" i dokumentet.

## Steg 3: Ändra språk
För att ändra språk för datum- och nummerformatering kan du ändra trådens nuvarande kultur. I det här exemplet kommer vi att ställa in språket till tyska ("de-DE"):

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

I ovanstående kod lagrar vi den aktuella kulturen och ställer sedan in den aktuella trådens kultur till tyska.

## Steg 4: Utför Mail Merge
Utför en kopplingsoperation och ange datumvärdet för fältet "Datum":

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

I det här kodavsnittet kör vi sammankopplingsoperationen och anger det aktuella datumet som värde för fältet "Datum".

## Steg 5: Återställ den ursprungliga lokalen
När sammanslagningen är klar återställer du den ursprungliga kulturen för tråden:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

I ovanstående kod återställer vi trådens ursprungliga kultur.

## Steg 6: Spara dokumentet
Spara det ändrade dokumentet till en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### Exempel på källkod för att ändra språk med Aspose.Words för .NET
Här är den fullständiga källkoden för att ändra språket i Word-dokument med Aspose.Words för .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du ändrar språket i Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide och använda den medföljande källkoden kan du nu styra formateringen av datum och siffror under kopplingsoperationer. Anpassa språket efter dina krav för att säkerställa korrekt och konsekvent formatering i dina dokument.
