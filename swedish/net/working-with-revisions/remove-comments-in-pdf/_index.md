---
title: Ta bort kommentarer i pdf-fil
linktitle: Ta bort kommentarer i pdf-fil
second_title: Aspose.Words Document Processing API
description: Ta bort kommentarer i en PDF-fil med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/remove-comments-in-pdf/
---

I den här steg-för-steg-guiden kommer vi att berätta hur du tar bort kommentarer i en PDF-fil med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

## Steg 1: Ladda dokumentet

Det första steget är att ladda dokumentet som innehåller kommentarerna.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Steg 2: Dölj kommentarer i PDF

Vi kommer att konfigurera layoutalternativet för att dölja kommentarer när PDF-filen genereras.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Steg 3: Spara dokumentet som PDF

Slutligen kommer vi att spara dokumentet i PDF-format genom att ta bort kommentarerna.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Markdown utdataformat

Utdata kan formateras i markdown för att förbättra läsbarheten. Till exempel :

```markdown
- Comments are hidden in the generated PDF.
```

### Exempel på källkod för Ta bort kommentarer i Pdf med Aspose.Words för .NET

Här är den fullständiga källkoden för att ta bort kommentarer i en PDF-fil med Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Dölj kommentarer i PDF:en.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Slutsats

den här handledningen lärde vi oss hur man tar bort kommentarer från en PDF-fil med Aspose.Words för .NET. Genom att använda lämpliga layoutalternativ kunde vi dölja kommentarerna när vi genererade PDF-filen. Aspose.Words för .NET erbjuder stor flexibilitet för att manipulera Word-filer och konvertera dem till olika format, inklusive PDF. Du kan nu tillämpa denna kunskap för att ta bort kommentarer i dina egna PDF-filer med Aspose.Words för .NET.

### Vanliga frågor för att ta bort kommentarer i pdf-fil

#### F: Hur laddar man upp ett dokument i Aspose.Words för .NET?

 A: Använd`Document` klass av Aspose.Words för .NET för att ladda ett dokument från en fil. Du kan ange hela dokumentsökvägen.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Hur döljer man kommentarer i PDF genererade med Aspose.Words för .NET?

 A: Använd`CommentDisplayMode`egendom av`LayoutOptions` objekt för att konfigurera hur kommentarer visas när PDF-filen genereras. För att dölja kommentarer, ställ in den här egenskapen till`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### F: Hur sparar jag dokument som PDF med Aspose.Words för .NET?

 A: Använd`Save` metod för`Document` objekt för att spara dokumentet i PDF-format. Ange hela sökvägen till PDF-filen.

```csharp
doc.Save("path/to/the/file.pdf");
```