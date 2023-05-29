---
title: Ta bort kommentarer i pdf
linktitle: Ta bort kommentarer i pdf
second_title: Aspose.Words för .NET API Referens
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

## Steg 3: Spara dokumentet som en PDF

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