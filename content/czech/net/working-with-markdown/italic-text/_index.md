---
title: Text kurzívou
linktitle: Text kurzívou
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se používat kurzívu pomocí Aspose.Words pro .NET Podrobný průvodce.
type: docs
weight: 10
url: /cs/net/working-with-markdown/italic-text/
---

V tomto příkladu vás provedeme tím, jak používat funkci textu kurzíva s Aspose.Words pro .NET. Kurzíva se používá ke zdůraznění určitých částí dokumentu.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Text pište kurzívou

 Kurzívou můžeme text nastavit nastavením písma`Italic`majetek do`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Příklad zdrojového kódu pro text kurzívou s Aspose.Words pro .NET


```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

// Udělejte text kurzívou.
builder.Font.Italic = true;
builder.Writeln("This text will be Italic");
```

gratuluji! Nyní jste se naučili používat funkci textu kurzíva s Aspose.Words pro .NET.


### FAQ

#### Otázka: Jak mohu v Aspose.Words napsat text kurzívou?

 Odpověď: Chcete-li text v Aspose.Words zobrazit kurzívou, můžete použít`Font.Italic` majetek z`Run` objekt. Tuto vlastnost můžete nastavit na`true` kurzívou konkrétní text. Můžete například použít`run.Font.Italic=true` zvýraznit kurzívou text obsažený v`Run` objekt.

#### Otázka: Je možné napsat kurzívou několik částí textu ve stejném odstavci?

 Odpověď: Ano, můžete kurzívou použít více částí textu v jednom odstavci pomocí více`Run` objektů. Můžete vytvořit více`Run` objekty a nastavte`Font.Italic`majetek do`true`pro každý objekt zvýraznit požadované části textu kurzívou. Poté je můžete přidat do odstavce pomocí`Paragraph.AppendChild(run)` metoda.

#### Otázka: Mohu v Aspose.Words napsat kurzívou text, který je v tabulce nebo buňce?

 Odpověď: Ano, text, který je v tabulce nebo buňce v Aspose.Words, můžete napsat kurzívou. Pomocí příslušných metod můžete přejít na požadovanou buňku nebo odstavec a poté použít formátování kurzívou pomocí`Font.Italic` majetek z`Run` nebo`Paragraph` objekt.