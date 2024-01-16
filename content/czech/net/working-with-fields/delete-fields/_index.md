---
title: Smazat pole
linktitle: Smazat pole
second_title: Aspose.Words API pro zpracování dokumentů
description: Průvodce krok za krokem pro odstranění slučovacích polí v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/delete-fields/
---

Vysvětlit, jak používat funkci "Odstranit pole" v Aspose. Words for .NET jsme vytvořili průvodce krok za krokem níže. 

Je důležité pečlivě sledovat každý krok, abyste dosáhli požadovaných výsledků. 

## Krok 1: Vytvoření nového dokumentu

V tomto fragmentu kódu začneme vytvořením nového prázdného dokumentu pomocí následujícího řádku: 

```csharp
Document doc = new Document();
```

## Krok 2: Odeberte slučovací pole

 K odstranění všech slučovacích polí přítomných v dokumentu používáme`DeleteFields()` funkce. 

To je zvláště užitečné, pokud chcete zachovat pouze statický obsah a odstranit veškeré informace o sloučení. 

### Příklad zdrojového kódu pro odstranění polí pomocí Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Načíst existující dokument.
Document doc = new Document(dataDir + "YourDocument.docx");

// Odstraňte slučovací pole.
doc.MailMerge.DeleteFields();

// Uložte upravený dokument.
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

 V našem příkladu nejprve načteme existující dokument před voláním`DeleteFields()`. Nakonec upravený dokument uložíme s novým názvem souboru. 

Chcete-li efektivně odstranit slučovací pole z dokumentu pomocí funkce „Odebrat pole“ Aspose.Words for .NET, vezměte si vodítko z tohoto příkladu. 

Vždy nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ vaší konkrétní cestou k adresáři. 

Náš průvodce implementací funkce "Delete Fields" prostřednictvím Aspose.Words pro .NET byl tímto uzavřen.

### FAQ

#### Otázka: Co je pole v Aspose.Words?

A: Pole v Aspose.Words je struktura dokumentu, která představuje automaticky generovaný text nebo vypočítanou hodnotu. Pole se používají k zobrazení dynamických informací v dokumentu, jako jsou čísla stránek, data, pole hromadné korespondence atd.

#### Otázka: Jak odstranit pole v dokumentu aplikace Word pomocí Aspose.Words?

Odpověď: Chcete-li odstranit pole v dokumentu aplikace Word pomocí Aspose.Words, můžete postupovat takto:

1. Importujte třídu Document z oboru názvů Aspose.Words.
2. Vytvořte instanci dokumentu načtením existujícího dokumentu.
3. K odstranění všech polí z dokumentu použijte metodu RemoveFields.

#### Otázka: Mohu smazat konkrétní pole namísto odstranění všech polí z dokumentu?

Odpověď: Ano, můžete odstranit konkrétní pole namísto odstranění všech polí z dokumentu. Chcete-li to provést, musíte přistupovat ke každému poli jednotlivě a pomocí metody Odebrat je odebrat.

#### Otázka: Jak mohu zkontrolovat, zda pole existuje v dokumentu aplikace Word před jeho odstraněním?

Odpověď: Chcete-li zkontrolovat, zda pole v dokumentu aplikace Word před jeho odstraněním existuje, můžete k vyhledání zadaného pole použít metodu Contains kolekce Fields. Tato metoda vrací booleovskou hodnotu označující, zda pole existuje nebo ne.

#### Otázka: Jaké jsou účinky odstranění pole na zbytek dokumentu?

Odpověď: Když odstraníte pole v dokumentu aplikace Word, pole se z dokumentu odstraní a vygenerovaný text nebo vypočítaná hodnota přidružená k poli se odstraní. To může ovlivnit rozvržení dokumentu, protože obsah generovaný polem bude smazán.