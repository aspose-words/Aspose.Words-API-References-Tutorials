---
title: Räkna upp egenskaper
linktitle: Räkna upp egenskaper
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att räkna upp dokumentegenskaper med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-properties/enumerate-properties/
---

I den här handledningen går vi igenom C#-källkoden för att räkna upp dokumentegenskaper med Aspose.Words för .NET. Denna funktion låter dig komma åt inbyggda och anpassade egenskaper för ett dokument.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet vars egenskaper vi vill lista. Använd följande kod för att ladda dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Räkna upp egenskaper

Låt oss nu lista dokumentegenskaperna, både inbyggda och anpassade egenskaper. Använd följande kod:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Den här koden visar dokumentnamnet och listar sedan de inbyggda och anpassade egenskaperna med deras namn och värde.

### Exempel på källkod för Enumerate Properties med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Var noga med att ange rätt dokumentsökväg i`dataDir` variabel.

Du har nu lärt dig hur du räknar upp dokumentegenskaper med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt komma åt och se egenskaperna för dina egna dokument.

