---
title: Konvertera fält i dokument
linktitle: Konvertera fält i dokument
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg guide för att konvertera dokumentfält till text med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/convert-fields-in-document/
---

I den här handledningen kommer vi att guida dig steg för steg med hjälp av ConvertFieldsInDocument-funktionen i Aspose.Words för .NET-programvara. Vi kommer att förklara i detalj C#-källkoden som behövs för den här funktionen och tillhandahålla exempel på markdown-utdataformat.

## Steg 1: Förutsättningar
Innan du börjar, se till att du har följande:

- Aspose.Words för .NET installerat på din utvecklingsmaskin.
- Ett Word-dokument som innehåller länkade fält som du vill konvertera till text.
- En dokumentkatalog där du kan spara det transformerade dokumentet.

## Steg 2: Sätta upp miljön
Se till att du har konfigurerat din utvecklingsmiljö korrekt för att använda Aspose.Words för .NET. Importera de nödvändiga namnområdena och ange sökvägen till din dokumentkatalog.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 3: Ladda dokumentet
 Använd`Document` klass av Aspose.Words för att ladda Word-dokumentet som innehåller de länkade fälten du vill konvertera.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");
```

## Steg 4: Konvertera bundna fält till text
 Använd`Unlink()` metod för att konvertera alla fält av typen "OM" som påträffas i dokumentet till text. Denna metod används för att omvandla länkade fält till deras textinnehåll.

```csharp
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());
```

## Steg 5: Spara det transformerade dokumentet
 Använd`Save()` metod för att spara dokumentet med fälten konverterade till text i den angivna dokumentkatalogen.

```csharp
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Exempel på källkod för ConvertFieldsInDocument med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen ConvertFieldsInDocument:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(MyDir + "Linked fields.docx");

// Skicka lämpliga parametrar för att konvertera alla IF-fält som påträffas i dokumentet (inklusive sidhuvuden och sidfötter) till text.
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());

// Spara dokumentet med fält omvandlade till disk
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Slutsats
Aspose.Words för .NET:s ConvertFieldsInDocument-funktion är ett kraftfullt verktyg för att konvertera länkade fält i ett Word-dokument till text. 