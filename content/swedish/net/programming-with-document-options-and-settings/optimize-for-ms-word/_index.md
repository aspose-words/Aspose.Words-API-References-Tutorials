---
title: Optimera för Ms Word
linktitle: Optimera för Ms Word
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att optimera ett dokument för MS Word med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-options-and-settings/optimize-for-ms-word/
---

den här handledningen går vi igenom C#-källkoden för att optimera ett dokument för MS Word med Aspose.Words för .NET. Med den här funktionen kan du optimera ett dokument för en specifik version av MS Word.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet som vi vill optimera. Använd följande kod för att ladda dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Optimering för MS Word

Låt oss nu optimera dokumentet för en specifik version av MS Word. Använd följande kod för att utföra optimeringen:

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2016);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.OptimizeForMsWord.docx");
```

 Denna kod säger till Aspose.Words att optimera dokumentet för MS Word 2016. Du kan ersätta`MsWordVersion.Word2016` med den specifika version av MS Word du vill optimera.

### Exempel på källkod för Optimize For Ms Word med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2016);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.OptimizeForMsWord.docx");
   
```

 Var noga med att ange rätt dokumentsökväg i`dataDir` variabel.

Du har nu lärt dig hur du optimerar ett dokument för en specifik version av MS Word med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt optimera dina egna dokument för olika versioner av MS Word.