---
title: Vložit vložený obrázek do dokumentu aplikace Word
linktitle: Vložit vložený obrázek do dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vkládat vložené obrázky do dokumentů aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/add-content-using-documentbuilder/insert-inline-image/
---
V tomto obsáhlém tutoriálu se naučíte vkládat vložené obrázky do dokumentu aplikace Word pomocí Aspose.Words for .NET. Provedeme vás celým procesem a poskytneme vám potřebné úryvky kódu C#. Na konci této příručky budete moci přidávat obrázky přímo do textu vašich dokumentů.

## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Knihovna Aspose.Words for .NET nainstalovaná ve vašem systému.

## Krok 1: Vytvořte nový dokument a DocumentBuilder
Chcete-li začít, vytvořte nový dokument pomocí třídy Document a inicializujte objekt DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Vložte vložený obrázek
Dále použijte metodu InsertImage třídy DocumentBuilder k vložení vloženého obrázku do dokumentu. Jako parametr zadejte cestu k souboru obrázku:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Krok 3: Uložte dokument
Po vložení vloženého obrázku uložte dokument do souboru pomocí metody Save třídy Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Příklad zdrojového kódu pro vložení vloženého obrázku pomocí Aspose.Words pro .NET
Zde je kompletní zdrojový kód pro vložení vloženého obrázku pomocí Aspose.Words pro .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak vkládat vložené obrázky do dokumentu aplikace Word pomocí Aspose.Words for .NET. Pokud budete postupovat podle podrobného průvodce a pomocí poskytnutého zdrojového kódu, můžete nyní plynule přidávat obrázky do textu vašich dokumentů.

Vložené obrázky jsou užitečné pro různé scénáře, jako je přidávání ilustrací, log nebo jiných vizuálních prvků přímo do toku dokumentu.

### Časté dotazy pro vložení vloženého obrázku do dokumentu aplikace Word

#### Otázka: Mohu změnit velikost vložených obrázků v dokumentu aplikace Word?

Odpověď: Ano, velikost vložených obrázků můžete změnit pomocí Aspose.Words for .NET. Po vložení obrázku můžete upravit jeho velikost úpravou vlastností šířky a výšky objektu Shape představujícího obrázek.

#### Otázka: Je možné přidat alternativní text k vloženým obrázkům pro účely usnadnění?

Odpověď: Ano, k vloženým obrázkům můžete přidat alternativní text, abyste zlepšili přístupnost. Aspose.Words for .NET podporuje přidávání alternativního textu k obrázkům, což umožňuje čtečkám obrazovky a dalším pomocným technologiím popisovat obsah obrázku uživatelům se zrakovým postižením.

#### Otázka: Mohu na vložené obrázky použít formátování nebo styly?

A: Rozhodně! Aspose.Words for .NET poskytuje rozsáhlé možnosti formátování pro vložené obrázky. Na obrázky můžete použít různé styly, ohraničení, efekty a další atributy formátování, aby odpovídaly vizuálnímu návrhu vašeho dokumentu.

#### Otázka: Podporuje Aspose.Words for .NET vkládání obrázků ze streamu nebo bajtového pole?

Odpověď: Ano, pomocí Aspose.Words for .NET můžete vkládat vložené obrázky z proudů nebo bajtových polí. To vám umožní pracovat s obrázky načtenými z externích zdrojů nebo dynamicky generovanými obrázky.

#### Otázka: Mohu vkládat obrázky na konkrétní místa v textovém obsahu?

Odpověď: Ano, třída DocumentBuilder v Aspose.Words pro .NET poskytuje přesnou kontrolu nad pozicí vložení vložených obrázků. Můžete určit přesné umístění v textu, kam má být obrázek vložen.