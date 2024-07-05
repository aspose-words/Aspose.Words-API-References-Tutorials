---
title: Smazat sekci
linktitle: Smazat sekci
second_title: Aspose.Words API pro zpracování dokumentů
description: tomto kurzu se dozvíte, jak odstranit konkrétní sekci z dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-section/delete-section/
---

V tomto tutoriálu vám ukážeme, jak odstranit konkrétní část dokumentu aplikace Word pomocí knihovny Aspose.Words pro .NET. Odstranění oddílu může být užitečné pro přeuspořádání nebo odstranění určitých částí dokumentu. Provedeme vás krok za krokem, abychom vám pomohli pochopit a implementovat kód ve vašem projektu .NET.

## Předpoklady
Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words pro .NET nainstalovaná ve vašem projektu

## Krok 1: Vytvořte dokument a konstruktor
 Nejprve vytvoříme instanci`Document` třída a přidružená`DocumentBuilder` konstruktor pro sestavení dokumentu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 2: Přidejte obsah a sekce
 Dále použijeme`DocumentBuilder` konstruktor pro přidání obsahu a sekcí do dokumentu. V tomto příkladu přidáváme dva řádky textu a dvě sekce.

```csharp
builder.Writeln("Hello1");
doc.AppendChild(new Section(doc));
builder.Writeln("Hello2");
doc.AppendChild(new Section(doc));
```

## Krok 3: Smažte konkrétní sekci
 K odstranění konkrétní části dokumentu použijeme`RemoveAt` způsob dokumentu`Sections` kolekce s uvedením indexu sekce, kterou chcete odstranit.

```csharp
doc.Sections.RemoveAt(0);
```

### Ukázka zdrojového kódu pro Delete Section pomocí Aspose.Words for .NET 

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.Writeln("Hello1");
	doc.AppendChild(new Section(doc));
	builder.Writeln("Hello2");
	doc.AppendChild(new Section(doc));
	doc.Sections.RemoveAt(0);

```

## Závěr
V tomto tutoriálu jsme viděli, jak odstranit konkrétní sekci z dokumentu aplikace Word pomocí Aspose.Words for .NET. Odstranění oddílů vám umožňuje změnit uspořádání nebo odstranit určité části dokumentu. Neváhejte si tuto funkci přizpůsobit a používat podle svých konkrétních potřeb.

### FAQ

#### Otázka: Jaké jsou předpoklady pro odstranění konkrétní části v dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Než začnete, ujistěte se, že máte následující položky:
- Pracovní znalost programovacího jazyka C#
- Knihovna Aspose.Words for .NET nainstalovaná ve vašem projektu

#### Otázka: Jak vytvořit nový dokument a konstruktor v Aspose.Words pro .NET?

 A: Chcete-li vytvořit nový dokument a konstruktor v Aspose.Words pro .NET, můžete použít následující kód. Zde vytvoříme instanci`Document` třída a přidružená`DocumentBuilder` konstruktor pro sestavení dokumentu:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Otázka: Jak přidat obsah a sekce do dokumentu v Aspose.Words for .NET?

 A: Chcete-li přidat obsah a sekce do dokumentu v Aspose.Words pro .NET, můžete použít`DocumentBuilder` konstruktér. V tomto příkladu přidáme dva řádky textu a dvě sekce:

```csharp
builder. Writen("Hello1");
doc.AppendChild(new Section(doc));
builder. Writen("Hello2");
doc.AppendChild(new Section(doc));
```

#### Otázka: Jak odstranit konkrétní sekci v Aspose.Words pro .NET?

 A: Chcete-li z dokumentu v Aspose.Words for .NET odstranit určitou sekci, můžete použít`RemoveAt` způsob dokumentu`Sections` kolekce s uvedením indexu sekce, kterou chcete odstranit:

```csharp
doc.Sections.RemoveAt(0);
```