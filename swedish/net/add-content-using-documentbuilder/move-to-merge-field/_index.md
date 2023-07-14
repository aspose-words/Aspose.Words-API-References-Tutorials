---
title: Flytta till sammanfogningsfält
linktitle: Flytta till sammanfogningsfält
second_title: Aspose.Words Document Processing API
description: Lär dig hur du implementerar funktionen Move To Merge Field i Aspose.Words för .NET med hjälp av en steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/move-to-merge-field/
---

det här exemplet kommer vi att utforska funktionen Move To Merge Field i Aspose.Words för .NET. Aspose.Words är ett kraftfullt dokumentmanipuleringsbibliotek som gör det möjligt för utvecklare att skapa, ändra och konvertera Word-dokument programmatiskt. Funktionen Move To Merge Field låter oss navigera för att slå samman fält i ett dokument och utföra olika operationer på dem.


## Förklara källkoden steg för steg

Låt oss gå igenom källkoden steg för steg för att förstå hur man använder funktionen Move To Merge Field med Aspose.Words för .NET.

## Steg 1: Initiera dokument- och dokumentbyggaren

Initiera först Document- och DocumentBuilder-objekten:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2 Infoga ett sammanfogningsfält och lägga till text efter det

Använd metoden InsertField i klassen DocumentBuilder för att infoga ett sammanslagningsfält och lägg sedan till text efter det:

```csharp
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");
```

## Steg 3: Byggarens markör är för närvarande i slutet av dokumentet.

```csharp
Assert.Null(builder.CurrentNode);
```
## Steg 4: Flytta dokumentbyggarens markör till sammanslagningsfältet

För att flytta dokumentbyggarmarkören till sammanslagningsfältet, använd MoveToField-metoden för klassen DocumentBuilder:

```csharp
builder.MoveToField(field, true);
```

## Lägger till text direkt efter sammanslagningsfältet

När markören för dokumentbyggaren är inne i sammanslagningsfältet kan du lägga till text direkt efter den med hjälp av skrivmetoden:

```csharp
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

### Exempel på källkod för Move To Merge Field med Aspose.Words för .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga ett fält med DocumentBuilder och lägg till en serie text efter det.
Field field = builder.InsertField("MERGEFIELD field");
builder.Write(" Text after the field.");

// Byggarens markör är för närvarande i slutet av dokumentet.
Assert.Null(builder.CurrentNode);
// Vi kan flytta byggaren till ett fält som detta, placera markören på omedelbart efter fältet.
builder.MoveToField(field, true);

// Observera att markören är på en plats förbi FieldEnd-noden i fältet, vilket betyder att vi faktiskt inte är inne i fältet.
// Om vi vill flytta DocumentBuilder till inuti ett fält,
// vi måste flytta den till ett fälts FieldStart- eller FieldSeparator-nod med metoden DocumentBuilder.MoveTo().
Assert.AreEqual(field.End, builder.CurrentNode.PreviousSibling);
builder.Write(" Text immediately after the field.");
```

## Slutsats

vi har utforskat funktionen Move To Merge Field i Aspose.Words för .NET. Vi lärde oss hur man navigerar för att slå samman fält i ett dokument med klassen DocumentBuilder och utföra operationer på dem. Den här funktionen är användbar när du programmerar ordbehandling med sammanfogning

