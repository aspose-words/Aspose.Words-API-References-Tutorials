---
title: Aktualizujte Smart Art Drawing
linktitle: Aktualizujte Smart Art Drawing
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se aktualizovat kresbu Smart Art v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-shapes/update-smart-art-drawing/
---

Tento tutoriál vysvětluje, jak aktualizovat kresbu Smart Art v dokumentu aplikace Word pomocí Aspose.Words for .NET. Procházením tvarů v dokumentu a kontrolou, zda mají Smart Art, můžete aktualizovat kresbu Smart Art, aby odrážela všechny změny provedené v jejích datech.

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
Načtěte dokument aplikace Word, který obsahuje kresbu Smart Art pomocí`Document` konstruktor třídy.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Krok 3: Aktualizujte kresbu Smart Art
 Procházejte tvary v dokumentu pomocí`GetChildNodes` metoda s`NodeType.Shape` parametr. Zkontrolujte, zda má každý tvar Smart Art pomocí`HasSmartArt` vlastnost, a pokud je to pravda, zavolejte`UpdateSmartArtDrawing` způsob aktualizace výkresu Smart Art.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Příklad zdrojového kódu pro aktualizaci Smart Art Drawing pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

A je to! Úspěšně jste aktualizovali kresbu Smart Art v dokumentu aplikace Word pomocí Aspose.Words for .NET.