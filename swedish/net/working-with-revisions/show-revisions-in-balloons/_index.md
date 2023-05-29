---
title: Visa revisioner i ballonger
linktitle: Visa revisioner i ballonger
second_title: Aspose.Words för .NET API Referens
description: Visa revisioner i ballonger med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/show-revisions-in-balloons/
---

I den här steg-för-steg-guiden kommer vi att visa dig hur du visar ändringar i ballonger i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

## Steg 1: Ladda dokumentet

Det första steget är att ladda upp dokumentet som innehåller ändringarna.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Steg 2: Konfigurera alternativ för granskningsvisning

Vi kommer att konfigurera visningsalternativen för att göra ändringar synliga i ballonger.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Steg 3: Spara dokumentet i PDF-format

Slutligen kommer vi att spara dokumentet som en PDF med revisionerna som visas i ballonger.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Markdown utdataformat

Utdata kan formateras i markdown för att förbättra läsbarheten. Till exempel :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Exempel på källkod för Show Revisions In Balloons med Aspose.Words för .NET

Här är den fullständiga källkoden för att visa revisioner i ballonger i ett dokument med Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Render infoga revisioner inline, ta bort och formatera revisioner i ballonger.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Återger revisionsfält till höger på en sida.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```



