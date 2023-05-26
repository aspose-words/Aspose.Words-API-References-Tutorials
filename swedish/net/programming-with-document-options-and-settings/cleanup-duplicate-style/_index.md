---
title: Cleanup Duplicate Style
linktitle: Cleanup Duplicate Style
second_title: Aspose.Words för .NET API Referens
description: Steg för steg guide för att rensa upp dubbletter av stilar i ett dokument med Aspose.Words för .NET. Fullständig källkod ingår.
type: docs
weight: 10
url: /sv/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

I den här handledningen går vi igenom steg för steg C#-källkoden för att rensa upp dubbletter av stilar med Aspose.Words för .NET. Den här funktionen hjälper till att ta bort dubbletter av stilar från ett dokument.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet som vi vill rensa upp. Använd följande kod för att ladda dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Räkna stilar innan rengöring

Innan vi fortsätter med rengöringen kommer vi att räkna antalet stilar som finns i dokumentet. Använd följande kod för att visa antalet stilar:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Detta uttalande visar antalet stilar som finns i dokumentet.

## Steg 4: Rensa upp dubbletter av stilar

Låt oss nu rensa upp dubbletter av stilar från dokumentet. Använd följande kod för att utföra rensningen:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Den här koden rensar upp dubbletter av stilar från dokumentet med de angivna alternativen. I det här exemplet aktiverade vi`DuplicateStyle` möjlighet att rensa upp dubbletter av stilar.

## Steg 5: Räkna stilar efter rengöring

Efter att ha gjort städningen kommer vi att räkna antalet stilar igen för att kontrollera om det har minskat. Använd följande kod för att visa antalet nya stilar:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Detta uttalande visar antalet stilar som återstår efter rengöring.

### Exempel på källkod för Cleanup Duplicate Style med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Antal stilar före rengöring.
	Console.WriteLine(doc.Styles.Count);

	// Rensar dubbletter av stilar från dokumentet.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//Antalet stilar efter rengöring minskades.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```