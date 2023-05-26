---
title: Kommentar löst och svar
linktitle: Kommentar löst och svar
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du löser kommentarer och deras svar i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-comments/comment-resolved-and-replies/
---

I den här omfattande självstudien kommer du att lära dig hur du löser kommentarer och deras svar i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna hantera kommentarslösning och uppdatera statusen för kommentarer och deras svar.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Ladda dokumentet och åtkomstkommentarer
Börja med att ladda dokumentet som innehåller kommentarerna med klassen Document och komma åt kommentarsamlingen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Steg 2: Lös kommentarer och deras svar
Gå sedan igenom kommentarerna och deras svar för att markera dem som lösta:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

ovanstående kod får vi åtkomst till föräldrakommentaren och itererar genom dess svar. Vi kan hämta förälderns kommentar-ID och dess upplösningsstatus. Sedan uppdaterar vi "Klar"-märket för varje kommentarsvar för att indikera lösning.

## Steg 3: Spara dokumentet
Efter att ha löst kommentarerna och uppdaterat deras status, spara det ändrade dokumentet i en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Exempel på källkod för att lösa kommentarer och deras svar med Aspose.Words för .NET
Här är den fullständiga källkoden för att lösa kommentarer och deras svar med Aspose.Words för .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Kom ihåg att justera koden enligt dina specifika krav, inklusive sökvägen till dokumentfilen och ytterligare anpassning

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du löser kommentarer och deras svar i ett Word-dokument med Aspose.Words för .NET. Genom att följa steg-för-steg-guiden och använda den medföljande källkoden kan du nu hantera kommentarslösning och uppdatera statusen för kommentarer och deras svar enligt dina krav.

Kommentarsupplösning hjälper till att spåra och hantera feedback i ett dokument. Experimentera med olika kommentarstatusar och anpassa dem för att förbättra samarbetet och granska processer i dina dokument.
