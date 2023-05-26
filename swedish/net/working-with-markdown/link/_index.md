---
title: Länk
linktitle: Länk
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar länkar med Aspose.Words för .NET. Steg-för-steg guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/link/
---

det här exemplet kommer vi att gå igenom hur du använder länkfunktionen med Aspose.Words för .NET. Länkar används för att skapa klickbara referenser till webbplatser eller andra dokument.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Infoga en länk

 Vi kan infoga en länk med hjälp av`Insertlink` dokumentgeneratorns metod. Vi måste ange länktexten, här "Aspose", samt måladressen.

```csharp
builder.Insertlink("Aspose", "https://www.aspose.com", false);
```

### Exempel på källkod för länkar med Aspose.Words för .NET


```csharp
	// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
	DocumentBuilder builder = new DocumentBuilder();

	// Infoga länk.
	builder.Insertlink("Aspose", "https://www.aspose.com", false);
            
```
Grattis! Du har nu lärt dig hur du använder länkfunktionen med Aspose.Words för .NET.

