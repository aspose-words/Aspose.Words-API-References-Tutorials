---
title: Lägg till anpassade dokumentegenskaper
linktitle: Lägg till anpassade dokumentegenskaper
second_title: Aspose.Words Document Processing API
description: Steg för steg guide för att lägga till anpassade egenskaper till ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-properties/add-custom-document-properties/
---

I den här handledningen går vi igenom C#-källkoden för att lägga till anpassade egenskaper till ett dokument med Aspose.Words för .NET. Denna funktion låter dig lägga till anpassad information till dokumentet.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet som vi vill lägga till anpassade egenskaper till. Använd följande kod för att ladda dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Lägg till anpassade egenskaper

Låt oss nu lägga till anpassade egenskaper till dokumentet. Använd följande kod för att lägga till egenskaperna:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Den här koden kontrollerar först om egenskapen "Authorized" redan finns i de anpassade egenskaperna. Om det finns avbryts processen. Annars läggs de anpassade egenskaperna till i dokumentet.

### Exempel på källkod för Lägg till anpassade dokumentegenskaper med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Var noga med att ange rätt dokumentsökväg i`dataDir` variabel.

Du har nu lärt dig hur du lägger till anpassade egenskaper till ett dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt lägga till dina egna anpassade egenskaper till dina dokument.