---
title: Vložit pole autora
linktitle: Vložit pole autora
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit pole AUTHOR do dokumentů aplikace Word pomocí Aspose.Words for .NET. Chcete-li své dokumenty přizpůsobit, zadejte jméno autora.
type: docs
weight: 10
url: /cs/net/working-with-fields/insert-author-field/
---


Zde je podrobný návod k vysvětlení zdrojového kódu C# níže, který používá funkci "Vložit pole AUTHOR" Aspose.Words pro .NET. Ujistěte se, že pečlivě dodržujete každý krok, abyste dosáhli požadovaných výsledků.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém kódu musíte zadat adresář vašich dokumentů. Nahraďte hodnotu „VÁŠ ADRESÁŘ DOKUMENTŮ“ příslušnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření dokumentu a odstavce

Začneme vytvořením nového dokumentu a načtením prvního odstavce.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Krok 3: Vložte pole AUTHOR

 Používáme`AppendField()` metoda pro vložení pole AUTHOR do odstavce.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Poté nakonfigurujeme pole`AuthorName` vlastnost k určení jména autora.

```csharp
field. AuthorName = "Test1";
```

 Nakonec zavoláme`Update()` způsob aktualizace pole.

```csharp
field. Update();
```

### Příklad zdrojového kódu pro vložení pole AUTHOR s Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vytvoření dokumentu.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Vložte pole AUTOR.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

V tomto příkladu jsme vytvořili nový dokument, vložili pole AUTHOR, nakonfigurovali jméno autora a uložili dokument se zadaným názvem souboru.

Tímto končí náš průvodce používáním funkce "Vložit pole AUTHOR" s Aspose.Words pro .NET.

### FAQ

#### Otázka: Co je pole autora v Aspose.Words?

Odpověď: Pole autora v Aspose.Words je speciální pole, které automaticky vkládá a aktualizuje jméno autora do dokumentu aplikace Word. Často se používá k označení toho, kdo vytvořil nebo upravil dokument.

#### Otázka: Jak aktualizovat pole autora v dokumentu aplikace Word pomocí Aspose.Words?

Odpověď: Pole autora v dokumentu aplikace Word lze aktualizovat tak, aby odráželo jméno aktuálního autora. K tomu můžete použít metodu UpdateFields dostupnou ve třídě Document. Tato metoda aktualizuje všechna pole v dokumentu, včetně pole autora.

#### Otázka: Je možné upravit formát pole autora v dokumentu aplikace Word?

Odpověď: Ano, je možné upravit formát pole autora v dokumentu aplikace Word. Ve výchozím nastavení pole autora jednoduše zobrazuje jméno autora. Můžete však přidat další informace, jako je datum a čas úpravy pomocí možností formátování dostupných v Aspose.Words.

#### Otázka: Je pole autora citlivé na následné změny jména autora?

Odpověď: Ano, pole autor je citlivé na následné změny jména autora. Pokud změníte jméno autora ve vlastnostech dokumentu, pole autor se automaticky aktualizuje novým jménem při aktualizaci polí dokumentu.