---
title: Jasná kontrola obsahu
linktitle: Jasná kontrola obsahu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vymazat obsah ovládacího prvku v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-sdt/clear-contents-control/
---

Tento kurz ukazuje, jak vymazat obsah SDT v dokumentu aplikace Word pomocí Aspose.Words for .NET. Vymazáním obsahu SDT odstraníte veškerý text nebo podřízené uzly v ovládacím prvku obsahu.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtěte dokument a získejte StructuredDocumentTag
 Načtěte dokument aplikace Word pomocí`Document` konstruktor, předá cestu k dokumentu jako parametr. Poté načtěte požadované`StructuredDocumentTag` dokumentu. V tomto příkladu předpokládáme, že SDT je prvním podřízeným uzlem v dokumentu.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Krok 3: Vymažte obsah StructuredDocumentTag
 Vymažte obsah SDT pomocí`Clear` metoda. Tím se odstraní veškerý text nebo podřízené uzly v ovládacím prvku obsahu.

```csharp
sdt.Clear();
```

## Krok 4: Uložte dokument
 Uložte upravený dokument pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu dokument uložíme jako „WorkingWithSdt.ClearContentsControl.doc“.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Příklad zdrojového kódu pro Clear Contents Control pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

A je to! Úspěšně jste vymazali obsah StructuredDocumentTag v dokumentu aplikace Word pomocí Aspose.Words for .NET.