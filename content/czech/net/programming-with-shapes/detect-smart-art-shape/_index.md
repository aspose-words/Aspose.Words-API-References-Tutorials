---
title: Detekce Smart Art Shape
linktitle: Detekce Smart Art Shape
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se detekovat tvary Smart Art v dokumentu aplikace Word pomocí Aspose.Words for .NET a identifikovat grafické znázornění.
type: docs
weight: 10
url: /cs/net/programming-with-shapes/detect-smart-art-shape/
---

Tento tutoriál vysvětluje, jak detekovat tvary Smart Art v dokumentu aplikace Word pomocí Aspose.Words for .NET. Tvary Smart Art jsou grafické reprezentace používané k vizuální prezentaci informací a nápadů.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"` se skutečnou cestou k adresáři, kde je umístěn váš dokument.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vložte dokument
 Načtěte dokument aplikace Word pomocí`Document` konstruktor, předá cestu k dokumentu jako parametr.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Krok 3: Zjistěte tvary chytrého umění
 Iterujte podřízené uzly typu`Shape` v dokumentu pomocí`GetChildNodes`metoda. Zkontrolujte, zda má každý tvar Smart Art pomocí`HasSmart Art` vlastnictví.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Krok 4: Výstup výsledku
Vytiskněte počet tvarů pomocí Smart Art zjištěných v dokumentu.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Příklad zdrojového kódu pro Detect Smart Art Shape pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

A je to! Pomocí Aspose.Words for .NET jste ve svém dokumentu aplikace Word úspěšně detekovali tvary Smart Art.