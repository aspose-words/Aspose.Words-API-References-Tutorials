---
title: Vložit pole Zahrnout text bez Tvůrce dokumentů
linktitle: Vložit FieldIncludeText bez Tvůrce dokumentů
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit pole FieldIncludeText do dokumentů aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Zde je podrobný návod k vysvětlení zdrojového kódu C# níže, který používá funkci "Vložit pole FieldIncludeText" Aspose.Words for .NET. Ujistěte se, že pečlivě dodržujete každý krok, abyste dosáhli požadovaných výsledků.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém kódu musíte zadat adresář vašich dokumentů. Nahraďte hodnotu „VÁŠ ADRESÁŘ DOKUMENTŮ“ příslušnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření dokumentu a odstavce

Začneme vytvořením nového dokumentu a inicializací odstavce.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Krok 3: Vložení pole FieldIncludeText

 Používáme`AppendField()` metoda pro vložení pole FieldIncludeText do odstavce.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Poté nakonfigurujeme vlastnosti pole FieldIncludeText zadáním názvu záložky a názvu zdrojového souboru.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Dále přidáme odstavec do těla dokumentu.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Nakonec zavoláme`Update()` způsob aktualizace pole.

```csharp
fieldIncludeText.Update();
```

### Příklad zdrojového kódu pro vložení pole FieldIncludeText s Aspose.Words for .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvořte dokument a odstavec.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Vložte pole FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

V tomto příkladu jsme vytvořili nový dokument, inicializovali odstavec, vložili FieldIncludeTexten určující název záložky a název zdrojového souboru a uložili dokument se zadaným názvem souboru.

Tímto končí náš průvodce používáním funkce "Vložit FieldIncludeText" s Aspose.Words pro .NET.

### FAQ

#### Otázka: Jak mohu určit zdrojový soubor pro pole pro zahrnutí textu v Aspose.Words for .NET?

 Odpověď: Chcete-li zadat zdrojový soubor pro pole pro zahrnutí textu v Aspose.Words pro .NET, můžete použít`FieldIncludeText.SourceFullName`vlastnost pro nastavení úplné cesty ke zdrojovému souboru. Ujistěte se, že je zdrojový soubor přístupný a obsahuje obsah, který chcete zahrnout do pole pro zahrnutí textu.

#### Otázka: Mohu zahrnout text z makra do pole pro zahrnutí textu pomocí Aspose.Words for .NET?

 Odpověď: Ano, pomocí Aspose.Words for .NET můžete do pole pro zahrnutí textu zahrnout text z makra. Můžete použít`FieldIncludeText.IncludeText` vlastnost k určení názvu makra, jehož obsah má být zahrnut do pole.

#### Otázka: Ovlivňuje vložení textového pole bez tvůrce dokumentů strukturu dokumentu Word s Aspose.Words for .NET?

Odpověď: Vložení textového pole bez tvůrce dokumentu přímo neovlivní strukturu dokumentu aplikace Word. Do obsahu dokumentu však přidá nový prvek pole. Strukturu dokumentu můžete upravovat přidáním, odstraněním nebo úpravou stávajících prvků podle vašich potřeb.

#### Otázka: Mohu upravit vzhled pole pro zahrnutí textu v dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Pole pro zahrnutí textu přímo nepřizpůsobuje svůj vzhled v dokumentu aplikace Word. Můžete však formátovat zahrnutý text pomocí vlastností odstavce, vlastností písma a dalších objektů formátování dostupných v Aspose.Words for .NET.