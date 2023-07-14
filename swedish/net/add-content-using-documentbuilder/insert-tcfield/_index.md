---
title: Infoga TCField
linktitle: Infoga TCField
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar och manipulerar TCFields i Word-dokument med C# och Aspose.Words för .NET i den här steg-för-steg-guiden.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-tcfield/
---

I det här exemplet kommer vi att guida dig genom processen att använda funktionen Insert TCField i Aspose.Words för .NET. TCField representerar en innehållsförteckning i ett Word-dokument. Vi kommer att tillhandahålla en steg-för-steg-förklaring av C#-källkoden, tillsammans med den förväntade utdata i markdown-format. Låt oss börja!

## Steg 1: Initiera dokument- och dokumentbyggaren

För att börja måste vi initialisera dokumentet och dokumentbyggaren. Dokumentbyggaren är ett kraftfullt verktyg från Aspose.Words för .NET som låter oss konstruera och manipulera Word-dokument programmatiskt. Så här kan du göra det:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Sätta in TCField

 Därefter kommer vi att infoga TCField i dokumentet med hjälp av`InsertField` metod. TCField representerar en innehållsförteckning med den angivna inmatningstexten. Här är ett exempel:

```csharp
builder.InsertField("TC \"Entry Text\" \\f t");
```

Ovanstående kod kommer att infoga ett TCField med inmatningstexten "Entry Text" i dokumentet.

## Steg 3: Spara dokumentet

 Efter att ha infogat TCField kan vi spara dokumentet på en specifik plats med hjälp av`Save` metod. Se till att ange önskad sökväg och filnamn för utdatadokumentet. Här är ett exempel:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
```

Ovanstående kod kommer att spara dokumentet med TCField till den angivna katalogen.

## Utdata Markdown-format

När koden exekveras framgångsrikt kommer utdatadokumentet att innehålla en innehållsförteckning med den angivna inmatningstexten. TCField representeras som ett fält i Word-dokumentet, och det resulterande markdown-formatet kommer att bero på hur dokumentet bearbetas.

Observera att utdatadokumentet inte är direkt i markdown-format utan snarare i Word-format. Men när du konverterar Word-dokumentet till markdown med hjälp av lämpliga verktyg eller bibliotek, kommer TCField att bearbetas därefter.

### Exempel på källkod för Infoga TCField med Aspose.Words för .NET

Här är den kompletta källkoden för att infoga ett TCField med Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("TC \"Entry Text\" \\f t");

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
```

Ändra koden enligt dina krav och utforska andra funktioner som tillhandahålls av Aspose.Words för .NET.

Det är allt! Du har framgångsrikt lärt dig hur man infogar ett TCField med Aspose.Words för .NET.

