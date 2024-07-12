---
title: Visa alternativ
linktitle: Visa alternativ
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att konfigurera dokumentvisningsalternativ med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-options-and-settings/view-options/
---

I den här handledningen går vi igenom C#-källkoden för att konfigurera visningsalternativ med Aspose.Words för .NET. Med den här funktionen kan du anpassa visningsläget och zoomnivån i ett dokument.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet som vi vill konfigurera visningsalternativen för. Använd följande kod för att ladda dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Konfigurera visningsalternativ

Nu kommer vi att konfigurera alternativen för dokumentvisning. Använd följande kod för att ställa in visningsläge och zoomnivå:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Denna kod ställer in visningsläget till "Sidlayout" och zoomnivån till 50 %.

### Exempel på källkod för View Options med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Var noga med att ange rätt dokumentsökväg i`dataDir` variabel.

Du har nu lärt dig hur du konfigurerar dokumentvisningsalternativ med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt anpassa visningen av dina egna dokument.