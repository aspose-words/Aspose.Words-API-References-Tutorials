---
title: Přidat textový vodoznak se specifickými možnostmi
linktitle: Přidat textový vodoznak se specifickými možnostmi
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak přidat textový vodoznak se specifickými možnostmi pomocí Aspose.Words for .NET. Průvodce krok za krokem.
type: docs
weight: 10
url: /cs/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

V tomto tutoriálu vás provedeme přidáním textového vodoznaku se specifickými možnostmi pomocí Aspose.Words pro .NET. Textový vodoznak je text překrývající dokument, který označuje, že se jedná o koncept, důvěrnost atd.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Načtení dokumentu

Načteme existující dokument pomocí cesty dokumentu.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Krok 3: Přidejte textový vodoznak se specifickými možnostmi

 Vytvoříme instanci`TextWatermarkOptions` třídy a nastavte požadované možnosti pro textový vodoznak.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Krok 4: Uložte dokument

Nakonec můžeme dokument uložit s přidaným textovým vodoznakem.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Příklad zdrojového kódu pro přidání textového vodoznaku se specifickými možnostmi s Aspose.Words pro .NET

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

gratuluji! Nyní jste se naučili, jak přidat textový vodoznak se specifickými možnostmi pomocí Aspose.Words pro .NET.

