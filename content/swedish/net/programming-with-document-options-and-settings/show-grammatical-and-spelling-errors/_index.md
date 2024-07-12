---
title: Visa grammatiska och stavningsfel
linktitle: Visa grammatiska och stavningsfel
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att möjliggöra visning av grammatiska fel och stavfel i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

I den här handledningen går vi igenom C#-källkoden för att möjliggöra visning av grammatiska och stavningsfel med Aspose.Words för .NET. Den här funktionen låter dig visa grammatiska och stavfel i ett dokument.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet för vilket vi vill visa grammatiska och stavningsfel. Använd följande kod för att ladda dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Aktivera felvisning

Nu kommer vi att aktivera visningen av grammatiska och stavningsfel i dokumentet. Använd följande kod för att aktivera felvisning:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Denna kod möjliggör visning av grammatiska fel (`ShowGrammaticalErrors`) och stavfel (`ShowSpellingErrors`) i dokumentet.

### Exempel på källkod för Visa grammatiska och stavningsfel med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Var noga med att ange rätt dokumentsökväg i`dataDir` variabel.

Du har nu lärt dig hur du aktiverar visningen av grammatiska fel och stavfel i ett dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i den här handledningen kan du enkelt aktivera den här funktionen i dina egna dokument.