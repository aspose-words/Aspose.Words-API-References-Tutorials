---
title: Jämför för lika
linktitle: Jämför för lika
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att förklara C#-källkoden för Compare for Equals-funktionen med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/compare-documents/compare-for-equal/
---

I den här handledningen går vi igenom hur du använder funktionen Compare for Equal med Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa ändringarna.

## Steg 1: Dokumentjämförelse

 Börja med att ladda två dokument för att jämföra. I det här exemplet kommer vi att använda`Clone()` metod för att skapa en kopia av originaldokumentet. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document docA = new Document(dataDir + "Document.docx");
Document docB = docA.Clone();
```

## Steg 2: Dokumentjämförelse

 Vi kommer nu att använda`Compare()` metod för att jämföra de två dokumenten. Denna metod kommer att markera ändringarna i originaldokumentet. Här är hur:

```csharp
// Jämför dokumenten
docA.Compare(docB, "user", DateTime.Now);

// Kontrollera om dokumenten är lika
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are identical": "Documents are not identical");
```

### Exempel på källkod för Compare For Equal med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Compare for Equals med Aspose.Words för .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();
	
	// DocA innehåller nu ändringar som revisioner.
	docA.Compare(docB, "user", DateTime.Now);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

Med den här koden kommer du att kunna jämföra två dokument och avgöra om de är lika med Aspose.Words för .NET.

