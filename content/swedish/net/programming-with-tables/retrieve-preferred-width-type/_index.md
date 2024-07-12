---
title: Hämta önskad breddtyp
linktitle: Hämta önskad breddtyp
second_title: Aspose.Words Document Processing API
description: Lär dig hur du hämtar typen och önskat breddvärde för en cell i en Word-tabell med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/retrieve-preferred-width-type/
---

I den här handledningen kommer vi att lära oss hur du hämtar den föredragna breddtypen och dess värde från en tabellcell i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna hämta önskad breddtyp (absolut, relativ eller automatisk) och dess värde för en specifik cell i dina Word-dokumenttabeller.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Ladda dokumentet
Följ dessa steg för att starta ordbehandling med dokumentet:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet
Document doc = new Document(dataDir + "Tables.docx");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog och ange korrekt filnamn.

## Steg 3: Hämta önskad breddtyp och värde
Därefter hämtar vi den föredragna breddtypen och dess värde för en specifik tabellcell. Använd följande kod:

```csharp
// Hämta bordet
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Aktivera automatisk bordsjustering
table. AllowAutoFit = true;

//Hämta den första cellen i den första raden
Cell firstCell = table.FirstRow.FirstCell;

// Hämta önskad breddtyp och dess värde
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

 Här använder vi dokumentet för att hämta den första tabellen, sedan aktiverar vi automatisk tabellpassning med`AllowAutoFit` fast egendom. Sedan hämtar vi den första cellen i den första raden i tabellen. Från denna cell kan vi hämta den föredragna breddtypen med`PreferredWidth.Type` egendom och dess värde med`PreferredWidth.Value` fast egendom.

### Exempel på källkod för Hämta önskad breddtyp med Aspose.Words för .NET 

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Slutsats
I den här handledningen lärde vi oss hur man hämtar den föredragna breddtypen och dess värde från en tabellcell i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du hämta denna information för specifika celler i dina Word-dokumenttabeller.