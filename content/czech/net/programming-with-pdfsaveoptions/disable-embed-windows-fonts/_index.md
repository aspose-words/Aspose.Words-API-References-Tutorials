---
title: Zmenšete velikost PDF deaktivací vložených písem
linktitle: Zmenšete velikost PDF deaktivací vložených písem
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak zmenšit velikost PDF deaktivací vkládání písem Windows při převodu dokumentů do PDF pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

V tomto tutoriálu vás provedeme kroky ke zmenšení velikosti PDF pomocí deaktivace vkládání písem Windows do dokumentu PDF pomocí Aspose.Words for .NET. Zakázáním vkládání písem můžete zmenšit velikost generovaného souboru PDF. Postupujte podle následujících kroků:

## Krok 1: Načtení dokumentu

Začněte nahráním dokumentu, který chcete převést do PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Nezapomeňte zadat správnou cestu k dokumentu.

## Krok 2: Nastavte možnosti uložení PDF

Vytvořte instanci třídy PdfSaveOptions a zadejte způsob vkládání písem:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Tato možnost umožňuje deaktivovat integraci písem Windows ve vygenerovaném souboru PDF.

## Krok 3: Převeďte dokument do PDF

 Použijte`Save` metoda převodu dokumentu do PDF s uvedením možností převodu:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Ujistěte se, že jste zadali správnou cestu pro uložení převedeného PDF.

### Příklad zdrojového kódu pro Zakázat vkládání písem Windows pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro zakázání vkládání písem Windows do dokumentu PDF pomocí Aspose.Words for .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Výstupní PDF bude uloženo bez vkládání standardních písem systému Windows.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Pomocí těchto kroků můžete snadno zakázat vkládání písem Windows do dokumentu PDF pomocí Aspose.Words for .NET.


## Závěr

tomto tutoriálu jsme se naučili, jak zmenšit velikost souboru PDF zakázáním vkládání písem Windows pomocí Aspose.Words for .NET. Zakázáním vkládání písem můžete zmenšit velikost generovaného souboru PDF, což usnadňuje ukládání, sdílení a přenos souborů. Je však důležité si uvědomit, že zakázání vkládání písem systému Windows může způsobit změny vzhledu a formátování v konečném dokumentu PDF. Při používání této funkce nezapomeňte vzít v úvahu tyto důsledky. Neváhejte a prozkoumejte další funkce Aspose.Words for .NET pro optimalizaci generování vašich souborů PDF.

### Často kladené otázky

#### Otázka: Co zakazuje vkládání písem systému Windows do dokumentu PDF a proč je to důležité?
Odpověď: Zakázání vkládání písem systému Windows do dokumentu PDF je proces, který zabraňuje zahrnutí písem systému Windows do vygenerovaného souboru PDF. Tím se zmenší velikost souboru PDF odstraněním vložených dat písem systému Windows. To může být důležité pro zmenšení velikosti souborů PDF, což může usnadnit jejich ukládání, sdílení a rychlejší přenos.

#### Otázka: Jak mohu zakázat vkládání písem Windows do dokumentu PDF pomocí Aspose.Words for .NET?
Odpověď: Chcete-li zakázat vkládání písem Windows do dokumentu PDF pomocí Aspose.Words for .NET, postupujte takto:

 Načtěte dokument, který chcete převést do PDF, pomocí`Document` třída a cesta k dokumentu.

 Vytvořte instanci souboru`PdfSaveOptions` třídu a nastavte`FontEmbeddingMode`majetek do`PdfFontEmbeddingMode.EmbedNone`. Tím zakážete vkládání písem Windows do vygenerovaného souboru PDF.

 Použijte`Save` metoda`Document` objekt pro převod dokumentu do PDF s určením voleb převodu nakonfigurovaných dříve.

#### Otázka: Jaké jsou výhody zakázání vkládání písem systému Windows do dokumentu PDF?
Odpověď: Výhody zakázání vkládání písem systému Windows do dokumentu PDF jsou:

Zmenšená velikost souboru PDF: Zakázáním vkládání písem systému Windows se odstraní data vložených písem systému Windows, čímž se zmenší velikost generovaného souboru PDF.

Snazší ukládání: Menší soubory PDF se snáze ukládají, ukládají a přenášejí.

Rychlejší sdílení a přenos: Menší soubory PDF lze sdílet a přenášet rychleji, což šetří čas a zdroje.

#### Otázka: Jaké jsou důsledky zakázání vkládání písem systému Windows do dokumentu PDF?
Odpověď: Zakázání vkládání písem Windows do dokumentu PDF může vést k následkům, jako jsou:

Ztráta vzhledu a formátování: Pokud v systému, kde je PDF otevřen, nejsou k dispozici písma Windows uvedená v dokumentu, budou použita náhradní písma, což může mít za následek nesprávný vzhled a formátování. tvarově odlišný od očekávaných.

Problémy s čitelností: Pokud použitá náhradní písma nejsou tak čitelná jako původní písma, může to ovlivnit čitelnost textu v dokumentu PDF.