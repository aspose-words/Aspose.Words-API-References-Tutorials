---
title: Rozdělit dokument Word podle stránky
linktitle: Rozdělit dokument Word podle stránky
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak rozdělit dokument aplikace Word na jednotlivé stránky pomocí Aspose.Words for .NET. Toto výkonné API zjednodušuje proces rozdělování dokumentů, takže je efektivní a pohodlné.
type: docs
weight: 10
url: /cs/net/split-document/page-by-page/
---

V tomto tutoriálu vás provedeme tím, jak rozdělit dokument aplikace Word na jednotlivé stránky pomocí funkce zpracování dokumentů Aspose.Words for .NET. Chcete-li porozumět zdrojovému kódu a získat samostatné dokumenty pro každou stránku, postupujte podle následujících kroků.

## Krok 1: Načtení dokumentu

Chcete-li začít, zadejte adresář pro váš dokument a načtěte dokument do objektu Document. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Krok 2: Rozdělení dokumentu podle stránek

Nyní projdeme každou stránku dokumentu a rozdělíme dokument na jednotlivé stránky. Zde je postup:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Uložte každou stránku jako samostatný dokument.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Příklad zdrojového kódu pro stránku po stránce pomocí Aspose.Words pro .NET

Zde je kompletní zdrojový kód pro funkci Page by Page Aspose.Words for .NET:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	// Uložte každou stránku jako samostatný dokument.
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

S tímto kódem budete moci rozdělit dokument aplikace Word na jednotlivé stránky pomocí Aspose.Words for .NET. V případě potřeby můžete také sloučit samostatné dokumenty.

## Závěr

Gratulujeme! Naučili jste se, jak rozdělit dokument aplikace Word na jednotlivé stránky pomocí funkce Stránka po stránce aplikace Aspose.Words for .NET. Podle poskytnutého zdrojového kódu můžete extrahovat každou stránku dokumentu a uložit je jako samostatné dokumenty.

Rozdělení dokumentu podle stránek může být užitečné, když potřebujete pracovat s konkrétními stránkami nebo distribuovat obsah granulárním způsobem. Aspose.Words for .NET poskytuje výkonné API, které zjednodušuje proces rozdělování dokumentů, takže je efektivní a pohodlné.

Neváhejte a prozkoumejte další funkce nabízené Aspose.Words pro .NET, abyste zlepšili své možnosti zpracování dokumentů a zefektivnili svůj pracovní postup.

### Nejčastější dotazy

#### Jak mohu rozdělit dokument na více stránek pomocí Aspose.Words for .NET?

 Chcete-li rozdělit dokument na více stránek, můžete použít`ExtractPages` metoda Aspose.Words API k získání rozsahu stránek. Zadáním počáteční stránky a počtu stránek k extrahování můžete vytvořit samostatné dokumenty pro každou stránku.

#### Mohu přizpůsobit výstupní formát při rozdělování dokumentu podle stránek?

Ano, Aspose.Words for .NET podporuje různé výstupní formáty při rozdělování dokumentu podle stránek. Každou stránku můžete uložit jako samostatný dokument ve formátech jako DOCX, PDF, HTML a dalších, v závislosti na vašich požadavcích.

#### Mohu rozdělit dokument podle určitého rozsahu stránek?

Absolutně! Aspose.Words for .NET umožňuje rozdělit dokument podle určitého rozsahu stránek. Úpravou počáteční stránky a počtu stránek k extrahování můžete přesně definovat rozsah stránek pro rozdělení dokumentu.

#### Je možné sloučit rozdělené dokumenty zpět do jednoho dokumentu?

Ano, rozdělené dokumenty můžete sloučit zpět do jednoho dokumentu pomocí funkce sloučení, kterou poskytuje Aspose.Words pro .NET. Kombinací samostatných dokumentů můžete podle potřeby znovu vytvořit původní dokument nebo vytvořit nový dokument s jinou strukturou.