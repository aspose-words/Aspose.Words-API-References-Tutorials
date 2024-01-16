---
title: Detekce číslování s mezerami
linktitle: Detekce číslování s mezerami
second_title: Aspose.Words API pro zpracování dokumentů
description: Zjistěte, jak v Aspose.Words for .NET zjistit čísla seznamů s prázdnými znaky. Snadno vylepšete strukturu svých dokumentů.
type: docs
weight: 10
url: /cs/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
tomto tutoriálu prozkoumáme zdrojový kód C# poskytovaný pro funkci "Detekce číslování s prázdnými mezerami" s Aspose.Words pro .NET. Tato funkce umožňuje detekovat a vytvářet seznamy z textového dokumentu obsahujícího čísla seznamů následovaná mezerami.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že jste nastavili své vývojové prostředí s Aspose.Words for .NET. Ujistěte se, že jste přidali potřebné reference a importovali příslušné jmenné prostory.

## Krok 2: Vytvoření textového dokumentu

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

V tomto kroku vytvoříme textový řetězec, který simuluje textový dokument obsahující čísla seznamu následovaná mezerami. Používáme různé oddělovače seznamu, jako je tečka, pravá závorka, symbol odrážky a mezery.

## Krok 3: Konfigurace možností nahrávání

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

 V tomto kroku nakonfigurujeme možnosti načítání dokumentu. Vytváříme nový`TxtLoadOptions` objekt a nastavte`DetectNumberingWithWhitespaces`majetek do`true`. To umožní Aspose.Words detekovat čísla seznamu, i když za nimi následují mezery.

## Krok 4: Načtení a uložení dokumentu

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 V tomto kroku načteme dokument pomocí zadaného textového řetězce a možností načtení. Používáme a`MemoryStream` pro převod textového řetězce na paměťový proud. Následně výsledný dokument uložíme ve formátu .docx.

### Ukázkový zdrojový kód pro funkci detekce číslování bílých míst s Aspose.Words pro .NET.

```csharp

            
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Vytvořte dokument ve formátu prostého textu ve formě řetězce s částmi, které lze interpretovat jako seznamy.
// Při načítání budou Aspose.Words vždy detekovány první tři seznamy,
// Po načtení se pro ně vytvoří objekty seznamu.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// Čtvrtý seznam s mezerami mezi číslem seznamu a obsahem položky seznamu,
// bude detekováno jako seznam pouze v případě, že je "DetectNumberingWithWhitespaces" v objektu LoadOptions nastaveno na hodnotu true,
// abyste předešli tomu, že odstavce začínající čísly nebudou mylně rozpoznány jako seznamy.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Načtěte dokument při použití LoadOptions jako parametru a ověřte výsledek.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Nyní můžete spustit zdrojový kód pro načtení textového dokumentu obsahujícího čísla seznamů s mezerami a poté vytvořit dokument .docx s detekovanými seznamy. Výstupní soubor bude uložen do zadaného adresáře s názvem "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx".

## Závěr
V tomto tutoriálu jsme prozkoumali funkci detekce číslování mezer v Aspose.Words pro .NET. Naučili jsme se vytvářet seznamy z textového dokumentu obsahujícího čísla seznamů následovaná mezerami.

Tato funkce je mimořádně užitečná pro zpracování dokumentů obsahujících čísla seznamu formátovaná různými způsoby. Pomocí vhodných možností načítání je Aspose.Words schopen detekovat tato čísla seznamů, i když za nimi následují mezery, a převést je do strukturovaných seznamů v konečném dokumentu.

Použití této funkce vám může ušetřit čas a zlepšit efektivitu vašeho pracovního postupu. Můžete snadno extrahovat informace z textových dokumentů a převádět je na dobře strukturované dokumenty se správnými seznamy.

Nezapomeňte zvážit možnosti načítání, jako je konfigurace detekce vytáčení prázdného místa, abyste dosáhli požadovaných výsledků.

Aspose.Words for .NET nabízí mnoho pokročilých funkcí pro manipulaci a generování dokumentů. Dalším prozkoumáním dokumentace a příkladů poskytovaných Aspose.Words budete moci plně využít možnosti této výkonné knihovny.

Neváhejte tedy integrovat detekci číslování bílých znaků do svých projektů Aspose.Words for .NET a využijte jeho výhod k vytváření dobře strukturovaných a čitelných dokumentů.


