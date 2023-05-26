---
title: Rensa oanvända stilar och listor
linktitle: Rensa oanvända stilar och listor
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att rensa bort oanvända stilar och listor i ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

I den här handledningen går vi igenom C#-källkoden för att rensa bort oanvända stilar och listor med Aspose.Words för .NET. Den här funktionen låter dig ta bort stilar och listor som inte används i ett dokument.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget kommer vi att ladda Word-dokumentet som innehåller de oanvända stilarna och listorna som vi vill rensa upp. Använd följande kod för att ladda dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Räkna stilar och listor innan rengöring

Innan rengöring kommer vi att räkna antalet stilar och listor som finns i dokumentet. Använd följande kod för att visa räknarna:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Dessa instruktioner visar antalet stilar och listor som finns i dokumentet före rengöring.

## Steg 4: Rensa bort oanvända stilar och listor

Låt oss nu rensa bort oanvända stilar och listor från dokumentet. Använd följande kod för att utföra rensningen:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Denna kod rensar bort oanvända stilar och listor från dokumentet med de angivna alternativen. I det här exemplet aktiverade vi`UnusedStyles` alternativet för att ta bort oanvända stilar och inaktivera`UnusedLists` möjlighet att behålla listorna även om de inte används.

## Steg 5: Räkna stilar och listor efter rengöring

Efter att ha gjort rensningen kommer vi att räkna stilarna och listorna igen för att kontrollera om de har komprimerats. Använd följande kod för att visa de nya räknarna:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

Dessa instruktioner visar antalet stilar och listor som återstår efter rengöring.

### Exempel på källkod för rengöring av oanvända stilar och listor med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// I kombination med de inbyggda stilarna har dokumentet nu åtta stilar.
	// En anpassad stil markeras som "använd" medan det finns någon text i dokumentet
	// formaterad i den stilen. Det betyder att de 4 stilarna vi har lagt till för närvarande är oanvända.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Rensar oanvända stilar och listor från dokumentet beroende på givna CleanupOptions.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Var noga med att ange rätt dokumentsökväg i`dataDir` variabel.

Du har nu lärt dig hur du rensar bort oanvända stilar och listor från ett dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i den här handledningen kan du enkelt tillämpa den här funktionen på dina egna dokument.

