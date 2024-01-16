---
title: Neukládat obrázkovou odrážku
linktitle: Neukládat obrázkovou odrážku
second_title: Aspose.Words API pro zpracování dokumentů
description: Přečtěte si, jak zakázat ukládání odrážek obrázků v dokumentech aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-docsaveoptions/do-not-save-picture-bullet/
---

Obrázkové odrážky jsou běžně používanou funkcí v dokumentech aplikace Word pro přidání vlastních odrážek. V některých případech však může být nutné zakázat registraci odrážek obrázku při manipulaci s dokumenty pomocí knihovny Aspose.Words pro .NET. V tomto podrobném průvodci vysvětlíme, jak použít zdrojový kód Aspose.Words C# pro .NET k zakázání ukládání odrážek obrázku pomocí možností uložení DocSaveOptions.

## Porozumění knihovně Aspose.Words

Než se ponoříte do kódu, je důležité porozumět knihovně Aspose.Words pro .NET. Aspose.Words je výkonná knihovna pro vytváření, úpravu, převod a ochranu dokumentů aplikace Word na různých platformách včetně .NET. Nabízí mnoho funkcí pro manipulaci s dokumenty, jako je vkládání textu, změna formátování, přidávání oddílů a mnoho dalšího.

## Krok 1: Nastavení adresáře dokumentů

Prvním krokem je definovat adresář, kde jsou umístěny vaše dokumenty. Musíte zadat úplnou cestu k adresáři. Například :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů.

## Krok 2: Načtení dokumentu s obrázkovými odrážkami

Dále je potřeba načíst dokument s obrázkovými odrážkami. K načtení dokumentu ze souboru použijte třídu Document. Například :

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

V tomto příkladu načítáme dokument ze souboru "Image bullet points.docx"

  umístěné v adresáři dokumentů.

## Krok 3: Nakonfigurujte možnosti nahrávání

Nyní nakonfigurujeme možnosti uložení pro náš dokument. Pomocí třídy DocSaveOptions zadejte nastavení uložení. Například :

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };
```

tomto příkladu vytvoříme nový objekt DocSaveOptions a nastavíme vlastnost SavePictureBullet na false, abychom zakázali ukládání obrázkových odrážek.

## Krok 4: Povolte funkci „Neukládat obrázkovou odrážku“.

Abychom povolili funkci „Neukládat obrázkové odrážky“, již jsme nakonfigurovali možnosti ukládání s nastavením SavePictureBullet na hodnotu false. Tím je zajištěno, že odrážky obrázků nebudou uloženy ve finálním dokumentu.

## Krok 5: Uložte dokument

Nakonec můžete dokument uložit pomocí metody Save třídy Document. Zadejte úplnou cestu k souboru a požadovaný název souboru. Například :

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

Nezapomeňte nahradit "dataDir" cestou adresáře k vašim dokumentům.

## Příklad zdrojového kódu pro možnosti uložení DocSaveOptions s funkcí „Neukládat obrázkové odrážky“ pomocí Aspose.Words for .NET

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument s odrážkami obrázků
Document doc = new Document(dataDir + "Image bullet points.docx");

// Nakonfigurujte možnosti uložení pomocí funkce „Neukládat obrázkové odrážky“.
DocSaveOptions saveOptions = new DocSaveOptions { SavePictureBullet = false };

// Uložte dokument se zadanými možnostmi
doc.Save(dataDir + "WorkingWithDocSaveOptions.DoNotSavePictureBullet.docx", saveOptions);
```

## Závěr

této příručce jsme se zabývali tím, jak zakázat ukládání obrazových odrážek v dokumentu pomocí knihovny Aspose.Words pro .NET. Dodržováním uvedených kroků a použitím poskytnutého zdrojového kódu C# můžete tuto funkci snadno použít ve své aplikaci C#. Vypnutí ukládání obrázkových odrážek může být v některých situacích užitečné pro zachování struktury a formátování dokumentu bez ukládání obrázkových odrážek.