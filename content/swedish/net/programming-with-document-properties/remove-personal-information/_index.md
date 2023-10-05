---
title: Ta bort personlig information
linktitle: Ta bort personlig information
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att ta bort personlig information från ett dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-document-properties/remove-personal-information/
---

den här handledningen går vi igenom C#-källkoden för att ta bort personlig information från ett dokument med Aspose.Words för .NET. Den här funktionen låter dig ta bort känslig personlig information från ett dokument, till exempel författaridentifieringsdata.

## Steg 1: Projektinställning

För att komma igång, skapa ett nytt C#-projekt i din favorit-IDE. Se till att Aspose.Words för .NET-biblioteket refereras till i ditt projekt.

## Steg 2: Ladda dokumentet

I det här steget laddar vi upp Word-dokumentet från vilket vi vill ta bort personuppgifterna. Använd följande kod för att ladda dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

## Steg 3: Radera personlig information

 Nu kommer vi att möjliggöra borttagning av personlig information genom att ställa in`RemovePersonalInformation`egendom till`true`. Använd följande kod:

```csharp
doc.RemovePersonalInformation = true;
```

Denna kod aktiverar radering av personlig information i dokumentet.

## Steg 4: Spara dokumentet

Slutligen kommer vi att spara dokumentet med personuppgifterna borttagna. Använd följande kod:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Denna kod sparar dokumentet med den personliga informationen borttagen till en ny fil.

### Exempel på källkod för Ta bort personlig information med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Var noga med att ange rätt dokumentsökväg i`dataDir` variabel.

Du har nu lärt dig hur du tar bort personlig information från ett dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du enkelt ta bort känslig information från dina egna dokument.