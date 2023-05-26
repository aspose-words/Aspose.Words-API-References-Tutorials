---
title: Teckensnittsinställningar Standardinstans
linktitle: Teckensnittsinställningar Standardinstans
second_title: Aspose.Words för .NET API Referens
description: I den här handledningen lär du dig hur du konfigurerar standardteckensnittsinställningar i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fonts/font-settings-default-instance/
---

I den här handledningen går vi igenom hur du konfigurerar standardteckensnittsinställningar i ett Word-dokument med Aspose.Words-biblioteket för .NET. Med standardteckensnittsinställningarna kan du ange de teckensnittskällor som används när du laddar och renderar dokument. Vi tar dig steg-för-steg för att hjälpa dig förstå och implementera koden i ditt .NET-projekt.

## Förutsättningar
Innan du börjar, se till att du har följande saker:
- Har praktiska kunskaper i programmeringsspråket C#
- Aspose.Words-biblioteket för .NET installerat i ditt projekt

## Steg 1: Definiera dokumentkatalogen
 Först måste du ställa in katalogsökvägen till platsen för ditt Word-dokument. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med rätt sökväg.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Konfigurera standardteckensnittsinställningar
 Därefter skapar vi en instans av`FontSettings` använder sig av`FontSettings.DefaultInstance`och sedan specificerar vi de teckensnittskällor som används när du laddar och renderar dokument. I det här exemplet använder vi en systemfontkälla och en mappteckensnittskälla.

```csharp
// Konfigurera standardteckensnittsinställningar
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Steg 3: Ladda upp dokument med teckensnittsinställningar
 Nu ska vi ladda dokumentet med`LoadOptions` och ange de teckensnittsinställningar som ska användas.

```csharp
// Ladda dokumentet med teckensnittsinställningarna
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Exempel på källkod för Font Settings Default Instance med Aspose.Words för .NET 
```csharp

// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Slutsats
I den här handledningen såg vi hur man konfigurerar standardteckensnittsinställningar i ett Word-dokument med Aspose.Words för .NET. Genom att ange de teckensnittskällor som används när du laddar och renderar dokument kan du styra hur teckensnitten ska se ut i dina dokument. Använd gärna den här funktionen för att anpassa teckensnittsinställningar i dina projekt.