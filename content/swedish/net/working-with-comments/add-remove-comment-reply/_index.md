---
title: Lägg till Ta bort kommentar Svara
linktitle: Lägg till Ta bort kommentar Svara
second_title: Aspose.Words Document Processing API
description: Lär dig hur du lägger till och tar bort kommentarsvar i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-comments/add-remove-comment-reply/
---

den här omfattande självstudien kommer du att lära dig hur du lägger till och tar bort kommentarsvar i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna hantera kommentarsvar och anpassa dem efter dina krav.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Ladda dokumentet
För att börja, ladda dokumentet som innehåller kommentarerna med klassen Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Steg 2: Öppna kommentaren och hantera svar
Öppna sedan kommentaren från dokumentet med metoden GetChild med parametern NodeType.Comment:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

För att ta bort ett svar från kommentaren, använd metoden RemoveReply och ange önskat svarsindex:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

För att lägga till ett nytt svar på kommentaren, använd AddReply-metoden och ange författarens namn, författarens initialer, datum och tid samt svarstext:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Steg 3: Spara dokumentet
När du har lagt till eller tagit bort kommentarsvar, spara dokumentet i en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Exempel på källkod för Lägg till och ta bort kommentarsvar med Aspose.Words för .NET
Här är den fullständiga källkoden för att lägga till och ta bort kommentarsvar med Aspose.Words för .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du lägger till och tar bort kommentarsvar i ett Word-dokument med Aspose.Words för .NET. Genom att följa steg-för-steg-guiden och använda den medföljande källkoden kan du nu hantera kommentarsvar och anpassa dem enligt dina krav.

Kommentarsvar möjliggör samarbetsdiskussioner och feedback i ett dokument. Experimentera med olika svarsförfattare, initialer, datum och texter för att förbättra samarbetet och kommunikationen i dina dokument.

### FAQ's

#### F: Hur kan jag lägga till en kommentar i Aspose.Words för .NET?

 S: För att lägga till en kommentar i Aspose.Words för .NET kan du använda`Comment.AddComment` metod som anger texten i kommentaren och var du vill lägga till den i dokumentet.

#### F: Hur kan jag ta bort en kommentar i Aspose.Words för .NET?

S: För att ta bort en kommentar i Aspose.Words för .NET kan du använda`Comment.Remove` metod som specificerar`Comment` objekt du vill ta bort.

#### F: Kan jag svara på en kommentar i Aspose.Words för .NET?

 S: Ja, du kan svara på en kommentar i Aspose.Words för .NET med hjälp av`Comment.AddReply` metod som anger svarstexten och var du vill lägga till den i dokumentet.

#### F: Hur kan jag komma åt befintliga kommentarer i Aspose.Words för .NET?

 S: Du kan komma åt befintliga kommentarer i Aspose.Words för .NET med hjälp av`CommentCollection` egendom av`Document` objekt. Detta gör att du kan bläddra bland alla kommentarer som finns i dokumentet.

#### F: Kan jag redigera kommentarstext i Aspose.Words för .NET?

 S: Ja, du kan redigera texten i en kommentar i Aspose.Words för .NET genom att öppna`Comment.Text` motsvarande egendom`Comment` objekt och ändra texten efter behov.