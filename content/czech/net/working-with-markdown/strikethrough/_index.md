---
title: Přeškrtnutí
linktitle: Přeškrtnutí
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat styl přeškrtnutého textu pomocí Aspose.Words for .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/strikethrough/
---


tomto příkladu vás provedeme tím, jak použít styl přeškrtnutého textu pomocí Aspose.Words for .NET. Přeškrtnutý text se používá k označení, že text je odstraněn nebo již není platný.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Použijte styl přeškrtnutého textu

 Styl přeškrtnutého textu povolíme nastavením`StrikeThrough` vlastnictvím`Font` namítat proti`true`.

```csharp
builder.Font.StrikeThrough = true;
```

## Krok 3: Přidejte přeškrtnutý text

 Nyní můžeme přidat přeškrtnutý text pomocí generátoru dokumentů`Writeln` metoda.

```csharp
builder.Writeln("This text will be StrikeThrough");
```


### Příklad zdrojového kódu pro přeškrtnutý text s Aspose.Words pro .NET

```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

// Přeškrtněte text.
builder.Font.StrikeThrough = true;
builder.Writeln("This text will be StrikeThrough");
```

gratuluji! Nyní jste se naučili, jak použít styl přeškrtnutého textu s Aspose.Words pro .NET.

### FAQ

#### Otázka: Jak mohu přidat přeškrtnutý text do Aspose.Words?

 A: Chcete-li přidat přeškrtnutý text do Aspose.Words, můžete použít`Font.StrikeThrough` vlastnictvím`Run`objekt. Tuto vlastnost můžete nastavit na`true` přidat přeškrtnutý text ke konkrétnímu textu. Můžete například použít`run.Font.StrikeThrough=true` přidat přeškrtnutý text do`Run` objekt.

#### Otázka: Je možné přidat přeškrtnutý text k několika částem textu ve stejném odstavci?

 Odpověď: Ano, můžete přidat přeškrtnutý text do více částí textu v jednom odstavci pomocí více`Run` objektů. Můžete vytvořit více`Run` objekty a nastavte`Font.StrikeThrough`majetek do`true` pro každý objekt přidat přeškrtnutý text do požadovaných částí textu. Poté je můžete přidat do odstavce pomocí`Paragraph.AppendChild(run)` metoda.

#### Otázka: Mohu přidat přeškrtnutý text k textu, který je v tabulce nebo buňce v Aspose.Words?

 Odpověď: Ano, k textu, který je v tabulce nebo buňce v Aspose.Words, můžete přidat přeškrtnutý text. Můžete přeskočit na požadovanou buňku nebo odstavec pomocí vhodných metod a poté použít formátování přeškrtnutého textu pomocí`Font.StrikeThrough` vlastnictvím`Run` nebo`Paragraph` objekt.