---
title: Ställ in relativ horisontell eller vertikal position
linktitle: Ställ in relativ horisontell eller vertikal position
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ställer in den relativa horisontella eller vertikala positionen för en tabell i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

I den här handledningen ska vi lära oss hur man ställer in den relativa horisontella eller vertikala positionen för en tabell i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna ställa in den relativa horisontella eller vertikala positionen för din tabell i dina Word-dokument.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Ladda dokumentet
Följ dessa steg för att starta ordbehandling med dokumentet:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog och ange korrekt filnamn.

## Steg 3: Ställa in bordets relativa position
Därefter ställer vi in den relativa horisontella eller vertikala positionen för tabellen. Använd följande kod:

```csharp
// Hämta bordet
Table table = doc.FirstSection.Body.Tables[0];

//Definition av bordets relativa horisontella position
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Definiera tabellens relativa vertikala position
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Här använder vi dokumentet för att hämta den första tabellen från brödtexten i det första avsnittet. Därefter ställer vi in den relativa horisontella positionen för bordet med`HorizontalAnchor` egendom med hjälp av`RelativeHorizontalPosition.Column` värde. På samma sätt ställer vi in den relativa vertikala positionen för bordet med`VerticalAnchor` egendom med hjälp av`RelativeVerticalPosition.Page` värde.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara det ändrade dokumentet med den relativa positionen för tabellen definierad. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för Ange relativ horisontell eller vertikal position med Aspose.Words för .NET 

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man ställer in den relativa horisontella eller vertikala positionen för en tabell i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du tillämpa denna relativa position på dina tabeller i dina Word-dokument.