---
title: Směr textu dokumentu
linktitle: Směr textu dokumentu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak určit směr textu v dokumentech pomocí Aspose.Words for .NET. Vylepšete zobrazení pro jazyky se zápisem zprava doleva.
type: docs
weight: 10
url: /cs/net/programming-with-txtloadoptions/document-text-direction/
---

tomto tutoriálu prozkoumáme zdrojový kód C# poskytovaný pro funkci "Document Text Direction" s Aspose.Words for .NET. Tato funkce umožňuje určit směr textu v dokumentu, což je užitečné zejména pro jazyky, které jsou psány zprava doleva, jako je hebrejština nebo arabština.

## Krok 1: Nastavení prostředí

Než začnete, ujistěte se, že jste nastavili své vývojové prostředí s Aspose.Words for .NET. Ujistěte se, že jste přidali potřebné reference a importovali příslušné jmenné prostory.

## Krok 2: Konfigurace možností nahrávání

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

 V tomto kroku nakonfigurujeme možnosti načítání dokumentu. Vytváříme nový`TxtLoadOptions` objekt a nastavte`DocumentDirection`majetek do`DocumentDirection.Auto`. Tato hodnota říká Aspose.Words, aby automaticky určil směr textu na základě obsahu dokumentu.

## Krok 3: Načtení dokumentu

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

 V tomto kroku načteme dokument pomocí`Document` a předání cesty k textovému souboru k načtení. Používáme také zadané možnosti načítání.

## Krok 4: Manipulujte s odstavcem a zobrazte směr textu

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

 V tomto kroku přistupujeme k prvnímu odstavci dokumentu pomocí`FirstSection` a`Body` vlastnosti. Dále přistupujeme k`ParagraphFormat.Bidi` vlastnost pro získání směru textu odstavce. Tuto hodnotu pak zobrazíme v konzoli.

## Krok 5: Uložte dokument

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

 V tomto posledním kroku uložíme výsledný dokument ve formátu .docx pomocí souboru`Save` a předání cesty k výstupnímu souboru.

Nyní můžete spustit zdrojový kód pro načtení textového dokumentu a určení směru textu. Výsledný dokument bude uložen do zadaného adresáře s názvem "WorkingWithTxtLoadOptions.DocumentTextDirection.docx".

### Ukázkový zdrojový kód pro funkci směrování textu dokumentu s Aspose.Words pro .NET.


```csharp

            
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Závěr

V tomto tutoriálu jsme prozkoumali funkci směrování textu dokumentu v Aspose.Words pro .NET. Naučili jsme se, jak určit směr textu v dokumentu, zejména u jazyků, které se píší zprava doleva, jako je hebrejština nebo arabština.

Tato funkce je nezbytná pro zajištění správného zobrazení textu ve vícejazyčných dokumentech. Pomocí vhodných možností načítání může Aspose.Words automaticky detekovat směr textu a aplikovat jej na dokument.

S Aspose.Words můžete snadno manipulovat se směrem textu ve vašich dokumentech, což uživatelům poskytuje plynulé a intuitivní čtení.

Je důležité poznamenat, že tato funkce je zvláště užitečná při zpracování textu v jazycích, které vyžadují specifický směr textu. Aspose.Words tento úkol usnadňuje tím, že poskytuje výkonné nástroje pro správu směru textu ve vašich dokumentech.

Nezapomeňte použít vhodné možnosti načítání, jako je nastavení automatického směru textu, abyste v dokumentech získali požadované výsledky.

Aspose.Words for .NET nabízí mnoho pokročilých funkcí pro manipulaci a generování dokumentů. Dalším prozkoumáním dokumentace a příkladů poskytovaných Aspose.Words budete moci plně využít možnosti této výkonné knihovny.

Neváhejte tedy integrovat směr textu dokumentu do svých projektů Aspose.Words for .NET a využijte jeho výhod k vytváření atraktivních a vysoce kvalitních vícejazyčných dokumentů.