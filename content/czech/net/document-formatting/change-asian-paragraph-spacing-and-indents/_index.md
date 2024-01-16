---
title: Změnit asijské mezery a odsazení v dokumentu aplikace Word
linktitle: Změnit asijské mezery a odsazení v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak změnit aspose.Words for .NET, jak změnit asijské mezery a odsazení v dokumentu aplikace Word.
type: docs
weight: 10
url: /cs/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
V tomto tutoriálu vás provedeme tím, jak změnit mezery a odsazení asijského odstavce pomocí Aspose.Words pro .NET. Chcete-li porozumět zdrojovému kódu a použít změny, postupujte podle následujících kroků.

## Krok 1: Načtení dokumentu

Chcete-li začít, zadejte adresář pro vaše dokumenty a načtěte dokument obsahující asijskou typografii do objektu Document. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Krok 2: Změna mezer a odsazení odstavců

Nyní upravíme mezery a odsazení prvního odstavce asijského dokumentu. Zde je postup:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Aktualizujte odstavecFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Aktualizujte odstavecFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //Aktualizujte odstavecFormat.FirstLineIndent
format.LineUnitBefore = 5; // Aktualizujte odstavecFormat.SpaceBefore
format.LineUnitAfter = 10; // Aktualizujte odstavecFormat.SpaceAfter
```

## Krok 3: Uložení dokumentu

 Po vložení textového pole formuláře uložte dokument na požadované místo pomocí`Save` metoda. Ujistěte se, že jste zadali správnou cestu k souboru:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Příklad zdrojového kódu pro změnu asijské mezery a odsazení odstavců pomocí Aspose.Words pro .NET

Zde je úplný zdrojový kód pro funkci Upravit asijské rozestupy a odsazení pomocí Aspose.Words pro .NET:

```csharp

	// Cesta k adresáři dokumentů.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagrafFormat.LeftIndent bude aktualizován
	format.CharacterUnitRightIndent = 10;      // OdstavecFormat.RightIndent bude aktualizován
	format.CharacterUnitFirstLineIndent = 20;  // ParagrafFormat.FirstLineIndent bude aktualizován
	format.LineUnitBefore = 5;                 // OdstavecFormat.SpaceBefore bude aktualizován
	format.LineUnitAfter = 10;                 // OdstavecFormat.SpaceAfter bude aktualizován

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

S tímto kódem budete moci změnit mezery a odsazení asijského odstavce pomocí Aspose.Words for .NET.

## Závěr

 V tomto tutoriálu jsme se naučili, jak změnit mezery a odsazení asijského odstavce pomocí Aspose.Words for .NET. Úpravou příslušných vlastností`ParagraphFormat`můžeme ovládat rozvržení a vzhled asijských odstavců v dokumentu aplikace Word. Tato funkce je užitečná pro přizpůsobení formátování textu asijskými znaky a dosažení požadované vizuální prezentace v dokumentech se smíšeným jazykovým obsahem.

### FAQ

#### Otázka: Co dělá funkce "Změna asijské mezery mezi odstavci a odsazení" v Aspose.Words pro .NET?

Odpověď: Funkce "Změna asijské mezery mezi odstavci a odsazení" v Aspose.Words for .NET umožňuje upravit vlastnosti mezer a odsazení asijského odstavce v dokumentu aplikace Word. Můžete upravit hodnoty levého a pravého odsazení, odsazení prvního řádku, mezeru před a mezeru za a řídit tak rozložení a vzhled odstavce.

#### Otázka: Jak změním mezery a odsazení asijského odstavce pomocí Aspose.Words for .NET?

 A: Chcete-li změnit mezery a odsazení asijského odstavce, musíte mít přístup k`ParagraphFormat`cílového odstavce a upravit jeho příslušné vlastnosti. V uvedeném příkladu kódu přistoupíme k prvnímu odstavci dokumentu a nastavíme`CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore` , a`LineUnitAfter` vlastnosti pro úpravu mezer a odsazení.

#### Otázka: Mohu tyto změny použít na další odstavce v dokumentu?

 Odpověď: Ano, tyto změny můžete použít na další odstavce v dokumentu tak, že otevřete jejich příslušné`ParagraphFormat` objektů. Vzorový kód se zaměřuje na první odstavec dokumentu, ale můžete upravit další odstavce úpravou indexu v`Paragraphs` sběr nebo použití jiných kritérií k výběru požadovaných odstavců.