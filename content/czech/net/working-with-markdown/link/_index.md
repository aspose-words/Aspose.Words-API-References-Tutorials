---
title: Odkaz
linktitle: Odkaz
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vkládat odkazy pomocí Aspose.Words pro .NET. Průvodce krok za krokem.
type: docs
weight: 10
url: /cs/net/working-with-markdown/link/
---

V tomto příkladu vás provedeme tím, jak používat funkci odkazů s Aspose.Words pro .NET. Odkazy se používají k vytvoření klikacích odkazů na webové stránky nebo jiné dokumenty.

## Krok 1: Použití generátoru dokumentů

Nejprve použijeme generátor dokumentů k přidání obsahu do našeho dokumentu.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Krok 2: Vložení odkazu

 Můžeme vložit odkaz pomocí`InsertHyperlink` metoda generátoru dokumentů. Musíme zadat text odkazu, zde „Aspose“, a také cílovou adresu URL.

```csharp
builder.InsertHyperlink("Aspose", "https://www.aspose.com", nepravda);
```

### Příklad zdrojového kódu pro odkazy s Aspose.Words pro .NET


```csharp
// K přidání obsahu do dokumentu použijte tvůrce dokumentů.
DocumentBuilder builder = new DocumentBuilder();

// Vložit odkaz.
builder.InsertHyperlink("Aspose", "https://www.aspose.com", nepravda);
```
gratuluji! Nyní jste se naučili, jak používat funkci odkazů s Aspose.Words pro .NET.


### FAQ

#### Otázka: Jak mohu vytvořit odkaz na URL v Aspose.Words?

 A: Chcete-li odkazovat na URL adresu v Aspose.Words, můžete použít`<a>` značka s`href` atribut obsahující adresu URL. Můžete například použít`<a href="https://www.aspose.com">Click Here</a>` hypertextový odkaz na adresu URL „https://www.example.com“ se zobrazeným textem „Klikněte sem“.

#### Otázka: Je možné vytvořit odkaz na interní záložku v Aspose.Words?

 Odpověď: Ano, v Aspose.Words je možné vytvořit odkaz na interní záložku. Můžete použít`<a>` značka s`href` atribut obsahující název záložky, kterému předchází hash (#). Například,`<a href="#bookmark1">Go to bookmark 1</a>` bude odkazovat na záložku s názvem "bookmark1" v dokumentu.

#### Otázka: Jak mohu přizpůsobit zobrazovaný text odkazu v Aspose.Words?

 A: Chcete-li upravit zobrazovaný text odkazu v Aspose.Words, můžete upravit obsah mezi`<a>` značky. Například,`<a href="https://www.aspose.com">Click here</a>` zobrazí text „Klikněte sem“ jako hypertextový odkaz.

#### Otázka: Mohu určit cíl pro odkaz v Aspose.Words?

Odpověď: Ano, můžete určit cíl pro odkaz v Aspose.Words pomocí`target` atribut toho`<a>` štítek. Například,`<a href="https://www.aspose.com" target="_blank">Open in new window</a>` otevře odkaz v novém okně nebo záložce.