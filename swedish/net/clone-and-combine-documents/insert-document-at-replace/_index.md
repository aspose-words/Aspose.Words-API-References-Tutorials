---
title: Infoga dokument vid ersätt
linktitle: Infoga dokument vid ersätt
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar ett dokument vid ersättning med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/clone-and-combine-documents/insert-document-at-replace/
---

den här handledningen går vi igenom hur du infogar ett dokument i ett annat dokument när du ersätter med hjälp av funktionen Infoga dokument vid ersättning i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och utföra dokumentinfogningen.

## Steg 1: Laddar huvuddokumentet

För att komma igång, ange katalogen för dina dokument och ladda huvuddokumentet i ett dokumentobjekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Steg 2: Konfigurera sök- och ersättalternativ

Nu kommer vi att konfigurera sök- och ersätt-alternativen genom att ange sökriktningen och ersätt återuppringning för att infoga ett dokument i ett annat dokument. Här är hur:

```csharp
// Konfigurera sök- och ersättalternativ.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Steg 3: Anropa ersättningsmetoden

Vi kommer nu att anropa ersätt-metoden för att hitta och ersätta den angivna texten med en tom sträng, med hjälp av de konfigurerade alternativen. Här är hur:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Exempel på källkod för Insert Document At Replace med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Infoga dokument när du ersätter Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Ställ in alternativ för sök och ersätt.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Kalla ersättningsmetoden.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```