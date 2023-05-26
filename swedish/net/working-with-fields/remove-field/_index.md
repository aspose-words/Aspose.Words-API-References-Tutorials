---
title: Ta bort fält
linktitle: Ta bort fält
second_title: Aspose.Words för .NET API Referens
description: I den här guiden kommer du att lära dig hur du tar bort ett specifikt fält i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/remove-field/
---
Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Fältborttagning" i Aspose.Words för .NET. Följ varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet

Vi börjar med att ladda det befintliga dokumentet från den angivna filen.

```csharp
Document doc = new Document(dataDir + "Various fields.docx");
```

## Steg 3: Ta bort fältet

 Vi väljer det första fältet i dokumentområdet och använder`Remove()` metod för att ta bort den.

```csharp
Field field = doc.Range.Fields[0];
field. Remove();
```

## Steg 4: Spara dokumentet

 Slutligen kallar vi`Save()` metod för att spara det ändrade dokumentet.

```csharp
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

### Exempel på källkod för radering av fält med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet.
Document doc = new Document(dataDir + "Various fields.docx");

// Val av fält som ska raderas.
Field field = doc.Range.Fields[0];
field. Remove();

// Spara dokumentet.
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

Följ dessa steg för att ta bort ett specifikt fält i ditt dokument med Aspose.Words för .NET.
