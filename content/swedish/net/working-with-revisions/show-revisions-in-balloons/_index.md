---
title: Visa revisioner i ballonger
linktitle: Visa revisioner i ballonger
second_title: Aspose.Words Document Processing API
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

## Slutsats

den här handledningen lärde vi oss hur man visar revisioner i ballonger i ett Word-dokument med Aspose.Words för .NET. Genom att använda lämpliga visningsalternativ kunde vi göra ändringarna synliga i bubblor med revisionsstaplar på höger sida. Aspose.Words för .NET erbjuder många kraftfulla funktioner för att manipulera Word-dokument, inklusive revisionshantering. Nu kan du använda denna kunskap för att visa revideringar i ballonger i dina egna Word-dokument med Aspose.Words för .NET.


### FAQ's

#### F: Hur laddar man upp ett dokument i Aspose.Words för .NET?

 A: Använd`Document` klass av Aspose.Words för .NET för att ladda ett dokument från en fil. Du kan ange hela dokumentsökvägen.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### F: Hur visar man revisioner i ballonger med Aspose.Words för .NET?

 A: Använd`ShowInBalloons` egendom av`RevisionOptions` objekt för att konfigurera visningen av revisioner i ballonger. Du kan ställa in den här egenskapen`ShowInBalloons.FormatAndDelete` för att visa revisioner i ballonger med raderings- och formateringsrevisioner.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### F: Hur sparar man ett dokument i PDF-format med Aspose.Words för .NET?

 A: Använd`Save` metod för`Document` objekt för att spara dokumentet i PDF-format. Du måste ange den fullständiga destinationssökvägen med tillägget ".pdf".

```csharp
doc.Save("path/to/destination/document.pdf");
```