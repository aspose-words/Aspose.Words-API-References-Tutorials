---
title: Ta bort innehållsförteckning
linktitle: Ta bort innehållsförteckning
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du tar bort innehållsförteckningen från ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/remove-content/remove-table-of-contents/
---

I den här handledningen går vi igenom hur du tar bort innehållsförteckningen från ett Word-dokument med hjälp av Aspose.Words-biblioteket för .NET. Innehållsförteckningen kan ibland vara överflödig eller onödig, och den här koden hjälper dig att ta bort den effektivt. Vi kommer att tillhandahålla en steg-för-steg-guide som hjälper dig att förstå och implementera koden i ditt eget .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt
- Ett Word-dokument som innehåller en innehållsförteckning som du vill ta bort

## Steg 1: Definiera dokumentkatalogen
 Först måste du ställa in katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda upp dokumentet
 Därefter kommer vi att ladda Word-dokumentet i en instans av`Document` klass med hjälp av`Load` metod.

```csharp
//Ladda dokumentet
Document doc = new Document(dataDir + "your-document.docx");
```

## Steg 3: Ta bort innehållsförteckningen
 För att ta bort innehållsförteckningen går vi igenom typen TOC (innehållsförteckning).`FieldStart` noder i dokumentet. Vi kommer att lagra dessa noder så att vi snabbt kan komma åt dem och skapa en lista med noder att ta bort.

```csharp
// Lagra FieldStart-noder för TOC-fält i dokumentet för snabb åtkomst.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Detta är en lista för att lagra noderna som finns i den angivna innehållsförteckningen. De kommer att raderas i slutet av denna metod.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Kontrollera om det angivna innehållsförteckningsindexet finns.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Det är säkrare att lagra dessa noder och ta bort dem alla i slutet.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // När vi stöter på en FieldEnd-nod av typen FieldTOC,
     // vi vet att vi är i slutet av nuvarande innehållsförteckning och vi slutar här.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Exempel på källkod för Ta bort innehållsförteckning med Aspose.Words för .NET 
```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
//Ladda dokumentet
Document doc = new Document(dataDir + "your-document.docx");

// Lagra FieldStart-noderna för innehållsförteckningsfält i dokumentet för snabb åtkomst.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Detta är en lista för att lagra noderna som finns i den angivna innehållsförteckningen. De kommer att tas bort i slutet av denna metod.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Se till att innehållsförteckningen som anges av det godkända indexet finns.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Det är säkrare att lagra dessa noder och ta bort dem alla på en gång senare.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// När vi stöter på en FieldEnd-nod av typen FieldTOC,
	// vi vet att vi är i slutet av nuvarande innehållsförteckning och slutar här.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## Slutsats
I den här handledningen presenterade vi en steg-för-steg-guide för att ta bort innehållsförteckningen från ett Word-dokument med hjälp av Aspose.Words-biblioteket för .NET. Genom att följa den medföljande koden och instruktionerna kan du enkelt ta bort innehållsförteckningen och förbättra layouten på ditt dokument. Kom ihåg att anpassa katalogsökvägen och filnamnen för att passa dina specifika behov.