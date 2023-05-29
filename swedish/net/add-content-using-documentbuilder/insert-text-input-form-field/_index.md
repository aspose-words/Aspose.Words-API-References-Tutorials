---
title: Infoga textinmatningsformulärfält
linktitle: Infoga textinmatningsformulärfält
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder Aspose.Words för .NET för att infoga formulärfält för textinmatning i Word-dokument med denna steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-text-input-form-field/
---

denna steg-för-steg-guide kommer vi att utforska hur du använder funktionen Infoga textinmatningsformulär i Aspose.Words för .NET för att lägga till och manipulera textinmatningsformulär i dina Word-dokument med hjälp av C#-källkoden. Fält för textinmatningsformulär låter användare skriva in anpassad text i ett dokument, vilket gör dem idealiska för att skapa interaktiva formulär och frågeformulär. Genom att följa instruktionerna nedan kommer du enkelt att kunna infoga och anpassa textinmatningsformulär i dina dokument. Låt oss börja!

## Introduktion till funktionen Infoga textinmatningsformulärfält i Aspose.Words för .NET

Funktionen Infoga formulärfält för textinmatning i Aspose.Words för .NET låter dig lägga till formulärfält för textinmatning programmatiskt till dina Word-dokument. Dessa formulärfält tillhandahåller ett interaktivt element där användare kan ange anpassad text eller data.

## Förstå kraven för att använda funktionen

Innan du fortsätter med implementeringen, se till att du uppfyller följande krav:

1. Aspose.Words för .NET-biblioteket installerat i ditt projekt.
2. Grundläggande kunskaper i programmeringsspråket C#.
3. Ett befintligt Word-dokument eller ett nytt dokument för att infoga textinmatningsformulärfältet.

Se till att du har dessa förutsättningar på plats för att fortsätta smidigt.

## Steg-för-steg-guide för att implementera Infoga textinmatningsformulärfält med C#-källkod

Följ stegen nedan för att implementera funktionen Infoga textinmatningsformulärfält med den medföljande C#-källkoden:

### Steg 1: Initiera dokument- och dokumentbyggaren

För att börja, initiera dokumentet och dokumentbyggaren. Dokumentbyggaren är ett kraftfullt verktyg från Aspose.Words för .NET som låter oss konstruera och manipulera Word-dokument programmatiskt. Använd följande kodavsnitt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

### Steg 2: Infoga fältet för textinmatningsformulär

 Därefter kommer vi att infoga formulärfältet för textinmatning i dokumentet med hjälp av`InsertTextInput` metod. Denna metod accepterar olika parametrar, inklusive namnet på formulärfältet, typen av formulärfält (i det här fallet,`TextFormFieldType.Regular`), standardvärdet och maximal längd. Här är ett exempel:

```csharp
builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);
```

Ovanstående kod kommer att infoga ett textinmatningsformulär med namnet "TextInput", ett standardvärde på "Hej" och ingen begränsning av maximal längd.

### Steg 3: Spara dokumentet

 När du har infogat formulärfältet för textinmatning sparar du dokumentet på önskad plats med hjälp av`Save` metod. Se till att ange rätt sökväg:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```

Denna kod kommer att spara dokumentet med det infogade textinmatningsformuläret på den angivna platsen.

### Exempel på källkod för Insert Text Input Form Field med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertTextInput("TextInput", TextFormFieldType.Regular, "", "Hello", 0);

doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
```
