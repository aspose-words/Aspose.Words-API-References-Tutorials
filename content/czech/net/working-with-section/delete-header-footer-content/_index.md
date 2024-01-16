---
title: Smazat obsah záhlaví a zápatí
linktitle: Smazat obsah záhlaví a zápatí
second_title: Aspose.Words API pro zpracování dokumentů
description: V tomto kurzu se dozvíte, jak odstranit obsah záhlaví a zápatí z dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-section/delete-header-footer-content/
---

tomto tutoriálu vám ukážeme, jak odstranit obsah záhlaví a zápatí z dokumentu aplikace Word pomocí knihovny Aspose.Words pro .NET. Odebrání obsahu ze záhlaví a zápatí může být užitečné, když chcete tyto prvky z dokumentu resetovat nebo odstranit. Provedeme vás krok za krokem, abychom vám pomohli pochopit a implementovat kód ve vašem projektu .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words pro .NET nainstalovaná ve vašem projektu
- Dokument aplikace Word obsahující záhlaví a zápatí, které chcete odstranit

## Krok 1: Definujte adresář dokumentů
 Nejprve musíte nastavit cestu k adresáři na umístění vašeho dokumentu aplikace Word. Nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s příslušnou cestou.

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vložte dokument a přejděte do sekce
 Dále načteme dokument aplikace Word do instance souboru`Document` třída. K první části dokumentu přistoupíme pomocí indexu 0.

```csharp
// Vložte dokument
Document doc = new Document(dataDir + "Document.docx");

// Vstupte do sekce
Section section = doc.Sections[0];
```

## Krok 3: Odstraňte obsah záhlaví a zápatí
 K odstranění obsahu záhlaví a zápatí ze sekce použijeme`ClearHeadersFooters` metoda.

```csharp
section.ClearHeadersFooters();
```

### Ukázkový zdrojový kód pro odstranění obsahu záhlaví zápatí pomocí Aspose.Words for .NET 

```csharp

// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## Závěr
tomto tutoriálu jsme viděli, jak odstranit obsah záhlaví a zápatí z dokumentu aplikace Word pomocí Aspose.Words for .NET. Odstranění obsahu ze záhlaví a zápatí vám umožní obnovit nebo odstranit tyto konkrétní prvky z dokumentu. Neváhejte si tuto funkci přizpůsobit a používat podle svých konkrétních potřeb.

### Časté dotazy k odstranění obsahu záhlaví zápatí

#### Otázka: Jak nastavit adresář dokumentů v Aspose.Words pro .NET?

 A: Chcete-li nastavit cestu k adresáři obsahujícímu vaše dokumenty, musíte nahradit`"YOUR DOCUMENT DIRECTORY"` v kódu s příslušnou cestou. Jak na to:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### Otázka: Jak načíst dokument a sekci přístupu v Aspose.Words pro .NET?

 A: Chcete-li načíst dokument aplikace Word do instance souboru`Document` třída tzv`doc` a přístup k první části dokumentu pomocí indexu 0, můžete použít následující kód:

```csharp
// Vložte dokument
Document doc = new Document(dataDir + "Document.docx");

// Vstupte do sekce
Section section = doc.Sections[0];
```

#### Otázka: Jak odstranit obsah záhlaví a zápatí v Aspose.Words for .NET?

 A: Chcete-li odstranit obsah záhlaví a zápatí ze sekce, můžete použít`ClearHeadersFooters` metoda:

```csharp
section.ClearHeadersFooters();
```

#### Otázka: Jak uložit upravený dokument v Aspose.Words pro .NET?

Odpověď: Jakmile odstraníte obsah záhlaví a zápatí, můžete upravený dokument uložit do souboru pomocí následujícího kódu:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```