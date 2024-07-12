---
title: Flytta nod i spårat dokument
linktitle: Flytta nod i spårat dokument
second_title: Aspose.Words Document Processing API
description: Flytta noder i ett spårat dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-revisions/move-node-in-tracked-document/
---

I den här steg-för-steg-guiden går vi igenom hur du flyttar en nod i ett spårat Word-dokument med Aspose.Words för .NET. Vi kommer att förse dig med den fullständiga källkoden och visa dig hur du formaterar markdown-utdata.

## Steg 1: Skapa dokumentet

Det första steget är att skapa ett nytt dokument och lägga till stycken.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## Steg 2: Spåra revisioner

Vi kommer att aktivera revisionsspårning i dokumentet.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## Steg 3: Flytta en nod

Vi kommer att flytta en nod (stycke) från en position till en annan medan vi genererar revisioner.

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## Steg 4: Sluta spåra recensioner

Vi kommer att sluta spåra revisioner i dokumentet.

```csharp
doc.StopTrackRevisions();
```

## Steg 5: Spara dokumentet

 När du har infogat formulärfältet för textinmatning sparar du dokumentet på önskad plats med hjälp av`Save`metod. Se till att ange rätt sökväg:

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Exempel på källkod för Move Node In Tracked Document med Aspose.Words för .NET

Här är den fullständiga källkoden för att flytta en nod i ett spårat dokument med Aspose.Words för .NET:


```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

// Börja spåra revisioner.
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

// Generera revisioner när du flyttar en nod från en plats till en annan.
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

// Stoppa processen med att spåra revisioner.
doc.StopTrackRevisions();

// Det finns ytterligare 3 stycken i intervallet för att flytta från.
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## Slutsats

I den här handledningen lärde vi oss hur man flyttar en nod i ett spårat Word-dokument med Aspose.Words för .NET. Genom att följa stegen för att skapa dokumentet, aktivera revisionsspårning, flytta noden och stoppa revisionsspårning, kunde vi utföra denna manipulation framgångsrikt. Aspose.Words för .NET är ett kraftfullt verktyg för ordbehandling med Word-dokument och erbjuder avancerade funktioner för att hantera revisioner. Nu kan du använda denna kunskap för att flytta noder i dina egna Word-dokument samtidigt som du spårar revisioner med Aspose.Words för .NET.

### FAQ's

#### F: Hur kan jag aktivera revisionsspårning i ett Aspose.Words for .NET-dokument?

 S: För att aktivera revisionsspårning i ett Aspose.Words för .NET-dokument kan du använda`StartTrackRevisions` metod för`Document` objekt. Denna metod tar som parametrar namnet på författaren till revisionerna och startdatumet för uppföljningen av revisionerna.

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### F: Hur kan jag flytta en nod i ett spårat dokument utan att generera revisioner?

 S: Om du vill flytta en nod i ett spårat dokument utan att generera revisioner kan du använda`Remove`och`InsertAfter` eller`InsertBefore` metoder för`Node` objekt. Till exempel, för att flytta ett stycke efter ett annat stycke, kan du använda följande kod:

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### F: Hur kan jag stoppa revisionsspårning i ett Aspose.Words för .NET-dokument?

 S: För att sluta spåra revisioner i ett Aspose.Words för .NET-dokument kan du använda`StopTrackRevisions` metod för`Document` objekt.

```csharp
doc.StopTrackRevisions();
```