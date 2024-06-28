---
title: Visa Dölj bokmärkt innehåll i Word-dokument
linktitle: Visa Dölj bokmärkt innehåll i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du dynamiskt visar eller döljer bokmärkt innehåll i Word-dokument med Aspose.Words för .NET med den här omfattande steg-för-steg-guiden.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

## Introduktion

Hallå där! Har du någonsin velat kontrollera synligheten för specifikt innehåll i ett Word-dokument baserat på vissa villkor? Med Aspose.Words för .NET kan du dynamiskt visa eller dölja bokmärkt innehåll med bara några rader kod. I den här handledningen går jag igenom processen steg-för-steg, så att du förstår varje del av koden. I slutet kommer du att vara ett proffs på att manipulera bokmärken i Word-dokument. Låt oss börja!

## Förutsättningar

Innan vi dyker in i handledningen, låt oss se till att du har allt du behöver:

1. Grundläggande kunskaper i C#: Du bör vara bekväm med C#-syntax och koncept.
2.  Aspose.Words för .NET: Ladda ner det[här](https://releases.aspose.com/words/net/) . Om du inte är redo att köpa kan du börja med en[gratis provperiod](https://releases.aspose.com/).
3. Visual Studio: Alla senaste versioner fungerar, men det rekommenderas att använda den senaste versionen.
4. .NET Framework: Se till att det är installerat på din dator.

Redo att börja? Bra! Låt oss börja med att importera de nödvändiga namnrymden.

## Importera namnområden

För att använda Aspose.Words för .NET måste vi importera de nödvändiga namnrymden. Detta steg säkerställer att vi har tillgång till alla klasser och metoder vi kommer att använda.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fields;
```

Dessa namnutrymmen är avgörande för att arbeta med Word-dokument och manipulera deras innehåll.

## Steg 1: Konfigurera dokumentet

Låt oss först skapa ett nytt Word-dokument och en dokumentbyggare. Dokumentbyggaren hjälper oss att enkelt lägga till och manipulera innehåll i dokumentet.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

I det här steget initierar vi ett nytt dokument och en dokumentbyggare. Detta förbereder vår miljö för vidare verksamhet.

## Steg 2: Lägga till bokmärkt innehåll

Därefter lägger vi till lite innehåll i dokumentet och skapar ett bokmärke runt det. Det här bokmärket hjälper oss att identifiera och manipulera innehållet.

```csharp
builder.Write("This is some text before the bookmark.");
builder.StartBookmark("MyBookmark");
builder.Write("This is the bookmarked content.");
builder.EndBookmark("MyBookmark");
builder.Write("This is some text after the bookmark.");
```

 Här lägger vi till lite text före och efter det bokmärkta innehållet. De`StartBookmark` och`EndBookmark` metoder definierar gränserna för bokmärket.

## Steg 3: Infoga ett villkorligt fält

För att kontrollera synligheten för det bokmärkta innehållet använder vi ett villkorsfält. Detta fält kommer att kontrollera ett villkor och visa eller dölja innehållet i enlighet med detta.

```csharp
builder.MoveToDocumentEnd();
Field field = builder.InsertField("IF \"", null);
builder.MoveTo(field.Start.NextSibling);
builder.InsertField("MERGEFIELD MyBookmark", null);
builder.Write("\" = \"true\" \"Visible\" \"Hidden\"");
```

I det här steget infogar vi ett IF-fält som kontrollerar värdet på bokmärket. Om värdet är "true", kommer det att visa "Visible"; annars kommer det att visa "Dold".

## Steg 4: Ordna om noder

Därefter måste vi ordna om noderna för att säkerställa att den villkorliga logiken tillämpas korrekt på det bokmärkta innehållet.

```csharp
Bookmark bm = doc.Range.Bookmarks["MyBookmark"];
Node currentNode = field.Start;
bool flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.Run && currentNode.ToString(SaveFormat.Text).Trim() == "\"")
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
    currentNode = nextNode;
}

Node endNode = bm.BookmarkEnd;
flag = true;

while (currentNode != null && flag)
{
    if (currentNode.NodeType == NodeType.FieldEnd)
        flag = false;

    Node nextNode = currentNode.NextSibling;
    bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
    endNode = currentNode;
    currentNode = nextNode;
}
```

Här flyttar vi runt noder för att se till att villkoret korrekt omfattar det bokmärkta innehållet.

## Steg 5: Kör sammanfogning av brev

Slutligen kommer vi att köra en sammankoppling för att ställa in värdet på bokmärket och avgöra om innehållet ska visas eller döljas.

```csharp
doc.MailMerge.Execute(new[] { "MyBookmark" }, new object[] { "true" });
```

Detta steg ställer in bokmärkesvärdet på "true", vilket gör innehållet synligt baserat på vårt tillstånd.

## Steg 6: Spara dokumentet

Efter alla manipulationer är det sista steget att spara det ändrade dokumentet.

```csharp
doc.Save("ShowHideBookmarkedContent.docx");
```

Här sparar vi dokumentet med ett beskrivande filnamn för att indikera ändringarna.

## Slutsats

 Och det är allt! Du har framgångsrikt lärt dig hur du visar eller döljer bokmärkt innehåll i ett Word-dokument med Aspose.Words för .NET. Denna handledning handlade om att skapa ett dokument, lägga till bokmärken, infoga villkorliga fält, arrangera om noder och köra en sammankoppling. Aspose.Words erbjuder en uppsjö av funktioner, så tveka inte att utforska[API dokumentation](https://reference.aspose.com/words/net/) för mer avancerade funktioner.

## Vanliga frågor

### 1. Vad är Aspose.Words för .NET?

Aspose.Words för .NET är ett kraftfullt bibliotek som låter utvecklare skapa, ändra och konvertera Word-dokument programmatiskt. Det används ofta för dokumentautomatiseringsuppgifter.

### 2. Kan jag använda Aspose.Words för .NET gratis?

 Du kan prova Aspose.Words för .NET med en[gratis provperiod](https://releases.aspose.com/). För långvarig användning måste du köpa en licens.

### 3. Hur ändrar jag andra egenskaper för ett bokmärke?

 Aspose.Words låter dig manipulera olika egenskaper hos ett bokmärke, såsom dess text och plats. Referera till[API dokumentation](https://reference.aspose.com/words/net/) för detaljerade instruktioner.

### 4. Hur får jag support för Aspose.Words för .NET?

Du kan få stöd genom att besöka[Aspose supportforum](https://forum.aspose.com/c/words/8).

### 5. Kan jag manipulera andra typer av innehåll med Aspose.Words för .NET?

Ja, Aspose.Words för .NET stöder olika typer av innehållsmanipulation, inklusive text, bilder, tabeller och mer.