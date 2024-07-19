---
title: Exportera textinmatningsformulärfält som text
linktitle: Exportera textinmatningsformulärfält som text
second_title: Aspose.Words Document Processing API
description: Steg för steg guide för att exportera textinmatningsformulärfält som vanlig text med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

I den här handledningen går vi igenom C#-källkoden för att exportera textinmatningsformulär som vanlig text med Aspose.Words för .NET. Med den här funktionen kan du exportera textinmatningsformulär som läsbar text istället för att exportera dem som HTML-inmatningselement.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda dokumentet för att exportera. Använd följande kod för att ladda dokumentet från en angiven katalog:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Denna kod skapar en instans av`Document` genom att ladda dokumentet från den angivna katalogen.

## Steg 3: Konfigurera alternativ för HTML-säkerhetskopiering

Nu kommer vi att konfigurera HTML-sparalternativ för att exportera textinmatningsformulär som vanlig text. Använd följande kod:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// Den angivna mappen måste finnas och vara tom.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Denna kod skapar en instans av`HtmlSaveOptions` och ställer in`ExportTextInputFormFieldAsText` möjlighet att`true` för att exportera textinmatningsformulärfält som vanlig text. Dessutom anger den mappen där de extraherade bilderna kommer att sparas.

## Steg 4: Konvertera och spara dokumentet till HTML

Slutligen kommer vi att konvertera dokumentet till HTML med hjälp av de HTML-sparalternativ som konfigurerats tidigare. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Den här koden konverterar dokumentet till HTML genom att exportera textinmatningsformulär som vanlig text och sparar den exporterade HTML-filen i den angivna katalogen.

### Exempel på källkod för Exportera textinmatningsformulärfält som text med Aspose.Words för .NET


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// Den angivna mappen måste finnas och bör vara tom.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Ställ in ett alternativ för att exportera formulärfält som vanlig text, inte som HTML-inmatningselement.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Var noga med att ange rätt sökväg till dokumentkatalogen i`dataDir` variabel.