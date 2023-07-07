---
title: Starta om lista vid varje avsnitt
linktitle: Starta om lista vid varje avsnitt
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du återställer en numrerad lista till varje avsnitt i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-list/restart-list-at-each-section/
---

I denna steg för steg handledning kommer vi att visa dig hur du återställer en numrerad lista till varje avsnitt i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte redan har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Skapa dokumentet och listan

Skapa först ett nytt dokument och lägg till en numrerad standardlista:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Steg 2: Lägga till objekt i listan

 Använd sedan a`DocumentBuilder` för att lägga till objekt i listan. Du kan använda en slinga för att lägga till flera objekt till listan:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

det här exemplet infogar vi en avsnittsbrytning efter den 15:e listposten för att illustrera omnumrering.

## Steg 3: Spara det ändrade dokumentet

Spara slutligen det ändrade dokumentet:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Så ! Du har framgångsrikt återställt en numrerad lista till varje avsnitt i ett Word-dokument med Aspose.Words för .NET.

### Exempel på källkod för att återställa listan vid varje avsnitt

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

Använd gärna den här koden i dina egna projekt och modifiera den för att passa dina specifika behov.

### FAQ's

#### F: Hur kan jag starta om en lista vid varje avsnitt i Aspose.Words?

 S: För att starta om en lista vid varje avsnitt i Aspose.Words, måste du skapa en instans av`List` klass och tilldela en numrerad lista till den. Då kan du använda`List.IsRestartAtEachSection` egenskap för att ange att numrering ska startas om vid varje avsnitt. Du kan associera den här listan med ett eller flera avsnitt av ditt dokument så att numreringen startas om korrekt vid varje avsnitt.

#### F: Kan jag anpassa numreringsformatet för listor i Aspose.Words?

 S: Ja, du kan anpassa numreringsformatet för listor i Aspose.Words. De`List` klass erbjuder flera fastigheter för detta, som t.ex`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`etc. Du kan använda dessa egenskaper för att ställa in listtyp (numrerad, punktlista, etc.), numreringsformat (arabiska siffror, romerska siffror, bokstäver, etc.) och andra numreringsformateringsalternativ.

#### F: Är det möjligt att lägga till ytterligare nivåer till en numrerad lista i Aspose.Words?

 S: Ja, det är möjligt att lägga till ytterligare nivåer till en numrerad lista i Aspose.Words. De`ListLevel` class låter dig ställa in formateringsegenskaper för varje nivå i listan. Du kan ställa in alternativ som prefix, suffix, justering, indrag, etc. Detta låter dig skapa listor med flera nivåer av hierarki.