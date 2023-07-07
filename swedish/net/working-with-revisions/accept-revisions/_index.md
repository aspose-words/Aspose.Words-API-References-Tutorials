---
title: Acceptera revisioner
linktitle: Acceptera revisioner
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du accepterar ändringar av ett Word-dokument med Aspose.Words för .NET
type: docs
weight: 10
url: /sv/net/working-with-revisions/accept-revisions/
---

I den här handledningen går vi igenom hur du accepterar revisioner av ett Word-dokument med hjälp av funktionen Acceptera ändringar i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och acceptera ändringar i dokumentet.

## Steg 1: Lägga till och redigera dokumentinnehåll

I det här exemplet skapar vi ett dokument och lägger till innehåll. Vi använder flera stycken för att illustrera ändringar och revideringar. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//Lägg till text i det första stycket och lägg sedan till ytterligare två stycken.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Steg 2: Spåra recensioner och lägg till recensioner

Vi aktiverar revisionsspårning och lägger till en revision i dokumentet. Här är hur:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Detta stycke är en revidering och kommer att ha motsvarande flagga "IsInsertRevision".
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Steg 3: Ta bort ett stycke och hantera ändringar

Vi tar bort ett stycke och letar efter sparade ändringar. Här är hur:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Eftersom vi spårar revisioner, finns stycket fortfarande i dokumentet, kommer att ha flaggan "IsDeleteRevision" inställd
// och kommer att visas som en recension i Microsoft Word, tills vi accepterar eller avvisar alla recensioner.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Steg 4: Acceptera ändringar

Vi accepterar alla ändringar i dokumentet. Här är hur:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Steg 5: Sluta spåra recensioner

Vi kommer att sluta spåra revisioner så att ändringar i dokumentet inte längre visas som revisioner. Här är hur:

```csharp
doc.StopTrackRevisions();
```
## Steg 6: Spara dokumentet

 När du har infogat formulärfältet för textinmatning sparar du dokumentet på önskad plats med hjälp av`Save` metod. Se till att ange rätt sökväg:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Exempel på källkod för Acceptera revisioner med Aspose.Words för .NET

Här är den fullständiga källkoden för att acceptera ändringar i ett dokument med Aspose.Words för .NET:


```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

//Lägg till text i det första stycket och lägg sedan till ytterligare två stycken.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// Vi har tre stycken, varav ingen är registrerad som någon typ av revision
// Om vi lägger till/tar bort något innehåll i dokumentet medan vi spårar revisioner,
// de kommer att visas som sådana i dokumentet och kan accepteras/avvisas.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Detta stycke är en revidering och kommer att ha flaggan "IsInsertRevision" inställd.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Skaffa dokumentets styckesamling och ta bort ett stycke.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Eftersom vi spårar revisioner, finns stycket fortfarande i dokumentet, kommer att ha "IsDeleteRevision" inställt
// och kommer att visas som en version i Microsoft Word tills vi accepterar eller avvisar alla versioner.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Raderingsrevisionsparagrafen tas bort när vi accepterar ändringar.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Att stoppa spårningen av revisioner gör att denna text visas som normal text.
//Revisioner räknas inte när dokumentet ändras.
doc.StopTrackRevisions();

// Spara dokumentet.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Slutsats

I den här handledningen lärde vi oss hur man accepterar revisioner i ett Word-dokument med hjälp av funktionen Acceptera revisioner i Aspose.Words för .NET. Vi har följt stegen för att lägga till och redigera dokumentinnehåll, spåra revisioner, ta bort ett reviderat stycke, acceptera alla ändringar och sluta spåra revisioner. Nu kan du tillämpa denna kunskap för att effektivt hantera revisioner i dina egna Word-dokument med Aspose.Words för .NET.

### Vanliga frågor

#### F: Hur aktiverar jag revisionsspårning i Aspose.Words för .NET?

#### Lösning 1:

 S: För att aktivera revisionsspårning i Aspose.Words för .NET, använd`StartTrackRevisions` metod för`Document` objekt och ange författarens namn och startdatum för revisionsspårning.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Lösning 2:

 S: Du kan också aktivera revisionsspårning med hjälp av`Document` konstruktör som accepterar`trackRevisions` och`author` parametrar.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### F: Hur accepterar jag alla ändringar i ett dokument med Aspose.Words för .NET?

 A: Använd`AcceptAllRevisions` metod för`Document` invända för att acceptera alla ändringar som görs i dokumentet.

```csharp
doc.AcceptAllRevisions();
```

#### F: Hur sparar jag ett ändrat dokument med godkända versioner?

 Använd`Save` metod för`Document` objekt för att spara det ändrade dokumentet med accepterade revisioner. Var noga med att ange rätt sökväg.

```csharp
doc.Save("path/to/the/document.docx");
```

#### F: Hur slutar jag spåra revisioner i Aspose.Words för .NET?

 A: Använd`StopTrackRevisions` metod för`Document` invända mot att stoppa spårningsrevisionerna.

```csharp
doc.StopTrackRevisions();
```

#### F: Hur tar jag bort ett reviderat stycke i ett dokument med Aspose.Words för .NET?

 S: För att ta bort ett reviderat stycke i ett dokument kan du använda`Remove` metod för styckeinsamlingen.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```