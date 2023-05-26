---
title: Ställ in bildmapp
linktitle: Ställ in bildmapp
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in bildmappen när du exporterar till Markdown med Aspose.Words för .NET. Anpassa placeringen av bilder för bättre organisation och integration.
type: docs
weight: 10
url: /sv/net/programming-with-markdownsaveoptions/set-images-folder/
---

Här är en steg-för-steg-guide för att förklara följande C#-källkod som hjälper till att ställa in bildmappen för Markdown-exportalternativ med Aspose.Words-biblioteket för .NET. Se till att du har inkluderat Aspose.Words-biblioteket i ditt projekt innan du använder den här koden.

## Steg 1: Ange sökväg till dokumentkatalogen

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Var noga med att ange rätt sökväg till din dokumentkatalog där dokumentet som innehåller bilderna finns.

## Steg 2: Ladda dokumentet som innehåller bilderna

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Vi laddar det angivna dokumentet som innehåller bilderna vi vill exportera med Markdown-alternativ.

## Steg 3: Ställ in bildmappen för Markdown-exportalternativ

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Vi skapar en instans av`MarkdownSaveOptions` och ställ in sökvägen till mappen bilder med hjälp av`ImagesFolder` fast egendom. Se till att ange rätt sökväg till mappen där du vill spara de exporterade bilderna.

## Steg 4: Spara dokumentet med Markdown-exportalternativ

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Vi sparar dokumentet i en minnesström med de angivna Markdown-exportalternativen. Du kan sedan använda flödet för att utföra andra operationer, som att spara Markdown-innehåll till en fil.

### Exempel på källkod för att ställa in bildmapp för MarkdownSaveOptions med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Den här källkoden visar hur man laddar ett dokument som innehåller bilder och sedan ställer in bildmappen för Markdown-exportalternativ. Med de angivna alternativen sparas dokumentet sedan i en minnesström. Detta gör att du kan anpassa platsen för bildmappen när du exporterar Markdown-innehåll.