---
title: Kloningsdokument
linktitle: Kloningsdokument
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du klona ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/clone-and-combine-documents/cloning-document/
---

den här handledningen kommer vi att berätta för dig hur du klona ett Word-dokument med hjälp av klonfunktionen i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och skapa en exakt kopia av ett befintligt dokument.

## Steg 1: Ladda dokumentet

För att komma igång, ange din dokumentkatalog och ladda det befintliga dokumentet i ett dokumentobjekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Steg 2: Klona dokumentet

Nu ska vi klona dokumentet och skapa en exakt kopia av det. Här är hur:

```csharp
Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.ClonageDocument.docx");
```

### Exempel på källkod för kloning av dokument med Aspose.Words för .NET

Här är den fullständiga källkoden för Aspose.Words dokumentkloningsfunktion för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";            
Document doc = new Document(MyDir + "Document.docx");

Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.CloningDocument.docx");
```

Med denna kod kommer du att kunna klona Word-dokument med Aspose.Words för .NET. Den exakta kopian av dokumentet kommer att sparas under ett nytt filnamn.

