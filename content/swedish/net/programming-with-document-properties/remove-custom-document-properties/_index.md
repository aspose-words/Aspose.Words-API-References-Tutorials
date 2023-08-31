---
title: Ta bort anpassade dokumentegenskaper
linktitle: Ta bort anpassade dokumentegenskaper
second_title: Aspose.Words Document Processing API
description: Steg-för-steg guide för att ta bort anpassade egenskaper från ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-properties/remove-custom-document-properties/
---

I den här handledningen går vi igenom C#-källkoden för att ta bort anpassade egenskaper från ett dokument med Aspose.Words för .NET. Med den här funktionen kan du ta bort en specifik anpassad egenskap från ett dokument.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet från vilket vi vill ta bort de anpassade egenskaperna. Använd följande kod för att ladda dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Ta bort anpassade egenskaper

Låt oss nu ta bort en specifik anpassad egenskap från dokumentet. Använd följande kod:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Den här koden tar bort den anpassade egenskapen "Authorized Date" från dokumentet. Du kan ersätta "Auktoriserat datum" med namnet på den anpassade egenskap du vill ta bort.

### Exempel på källkod för Ta bort anpassade dokumentegenskaper med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Var noga med att ange rätt dokumentsökväg i`dataDir` variabel.

Du har nu lärt dig hur du tar bort anpassade egenskaper från ett dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt ta bort anpassade egenskaper från dina egna dokument.