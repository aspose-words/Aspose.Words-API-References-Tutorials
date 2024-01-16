---
title: Vložit objekt OLE do dokumentu aplikace Word
linktitle: Vložit objekt OLE do dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit objekt OLE do dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-oleobjects-and-activex/insert-ole-object/
---

Zde je průvodce krok za krokem, který vysvětluje zdrojový kód C# níže, který ilustruje, jak vložit objekt OLE do dokumentu aplikace Word pomocí Aspose.Words for .NET.

## Krok 1: Importujte potřebné reference
Než začnete, ujistěte se, že jste do svého projektu naimportovali potřebné reference pro použití Aspose.Words for .NET. To zahrnuje import knihovny Aspose.Words a přidání požadovaných jmenných prostorů do zdrojového souboru.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Krok 2: Vytvořte nový dokument a generátor dokumentů
 V tomto kroku vytvoříme nový dokument pomocí`Document` třída a tvůrce dokumentů pomocí`DocumentBuilder` třída.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Vložte objekt OLE
 Použijte Tvůrce dokumentů`InsertOleObject` metoda pro vložení objektu OLE do dokumentu. Zadejte adresu URL objektu OLE, typ objektu, možnosti zobrazení a další nezbytná nastavení.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlsoubor", true, true, null);
```

## Krok 4: Uložte dokument
 Použijte dokument`Save` způsob uložení dokumentu do souboru.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Příklad zdrojového kódu pro vložení objektu OLE pomocí Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlsoubor", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

Toto je kompletní ukázka kódu pro vložení objektu OLE pomocí Aspose.Words for .NET. Nezapomeňte importovat potřebné reference a postupujte podle výše popsaných kroků k integraci tohoto kódu do vašeho projektu.

## Závěr

Závěrem lze říci, že vkládání objektů OLE do dokumentu aplikace Word je výkonná funkce, kterou nabízí Aspose.Words for .NET. Pomocí této knihovny můžete snadno vkládat objekty OLE, jako jsou soubory HTML, tabulky Excel, prezentace PowerPoint atd., do dokumentů aplikace Word.

V tomto článku jsme prošli podrobným průvodcem, který vysvětluje zdrojový kód v C#, který ukazuje, jak vložit objekt OLE do dokumentu aplikace Word. Probrali jsme potřebné reference, vytvoření nového dokumentu a generátoru dokumentů a kroky pro vložení objektu OLE a uložení dokumentu.

### Časté dotazy pro vkládání objektu OLE do dokumentu aplikace Word

#### Otázka: Jaké přihlašovací údaje musím importovat, abych mohl používat Aspose.Words pro .NET?

A: Chcete-li používat Aspose.Words pro .NET, musíte importovat následující odkazy:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Otázka: Jak vytvořit nový dokument a generátor dokumentů?

 Odpověď: Můžete vytvořit nový dokument pomocí`Document` třída a tvůrce dokumentů pomocí`DocumentBuilder` třídy, jak je uvedeno níže:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Otázka: Jak vložit objekt OLE do dokumentu?

 A: Použijte`InsertOleObject`metoda tvůrce dokumentů (`DocumentBuilder`) pro vložení objektu OLE do dokumentu. Zadejte adresu URL objektu OLE, typ objektu, možnosti zobrazení a další nezbytná nastavení. Zde je příklad:

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlsoubor", true, true, null);
```

#### Otázka: Jak uložit dokument?

 A: Použijte dokument`Save` způsob uložení dokumentu do souboru. Zde je příklad:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### Otázka: Můžete poskytnout úplný příklad vložení objektu OLE pomocí Aspose.Words for .NET?

Odpověď: Zde je kompletní ukázkový kód pro vložení objektu OLE pomocí Aspose.Words for .NET. Nezapomeňte importovat potřebné reference a postupujte podle výše popsaných kroků k integraci tohoto kódu do vašeho projektu:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlsoubor", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```
