---
title: Fältuppdateringskultur
linktitle: Fältuppdateringskultur
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du uppdaterar fältkultur i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/field-update-culture/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Field Culture Update" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa dokumentet och dokumentgeneratorn

Vi börjar med att skapa ett nytt dokument och en dokumentgenerator.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Infoga tidsfältet

 Vi använder`InsertField()` metod för att infoga ett tidsfält i dokumentet.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

Detta kommer att infoga ett tidsfält i dokumentet.

## Steg 4: Konfigurera fältuppdateringskulturen

Vi konfigurerar fältalternativen för att specificera att fältuppdateringskulturen ska baseras på fältkoden.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

Dessa alternativ bestämmer vilken kultur som används för att uppdatera fält.

### Exempel på källkod för uppdatering av fältkultur med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa dokumentet och dokumentgeneratorn.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga tidsfältet.
builder. InsertField(FieldType.FieldTime, true);

// Konfigurera fältuppdateringskulturen.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// Spara dokumentet.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

det här exemplet har vi skapat ett nytt dokument, infogat ett tidsfält och konfigurerat fältuppdateringskulturen. Sedan sparade vi dokumentet med ett angivet filnamn.

Detta avslutar vår guide om hur du använder funktionen "Update Field Culture" med Aspose.Words för .NET.