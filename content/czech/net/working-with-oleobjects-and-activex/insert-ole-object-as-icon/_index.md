---
title: Vložit OLE objekt do dokumentu aplikace Word jako ikonu
linktitle: Vložit OLE objekt do dokumentu aplikace Word jako ikonu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit objekt OLE do dokumentu aplikace Word jako ikonu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Zde je průvodce krok za krokem, který vysvětluje zdrojový kód C# níže, který ilustruje, jak vložit objekt OLE do dokumentu aplikace Word jako ikonu pomocí Aspose.Words for .NET.

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

## Krok 3: Vložte OLE objekt jako ikonu
 Použijte Tvůrce dokumentů`InsertOleObjectAsIcon` metoda pro vložení objektu OLE jako ikony do dokumentu. Zadejte cestu k souboru OLE, příznak zobrazení, cestu k ikoně a název vloženého objektu.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Krok 4: Uložte dokument
 Použijte dokument`Save` způsob uložení dokumentu do souboru.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Příklad zdrojového kódu pro vložení objektu OLE jako ikony pomocí Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

Toto je kompletní ukázka kódu pro vložení objektu OLE jako ikony pomocí Aspose.Words for .NET. Nezapomeňte importovat potřebné reference a postupujte podle výše popsaných kroků k integraci tohoto kódu do vašeho projektu.

## Závěr

Na závěr jsme prozkoumali podrobný návod, jak vložit objekt OLE jako ikonu do dokumentu aplikace Word pomocí Aspose.Words for .NET.

Podle těchto kroků budete moci úspěšně vložit objekt OLE jako ikonu do dokumentů aplikace Word pomocí Aspose.Words for .NET. Nezapomeňte importovat potřebné reference a pečlivě dodržujte pokyny, abyste získali požadované výsledky.

### Časté dotazy pro vložení ole objektu do dokumentu aplikace Word jako ikonu

#### Q. Jaké odkazy jsou potřebné k vložení objektu OLE jako ikony do dokumentu aplikace Word pomocí Aspose.Words for .NET?

A: Chcete-li používat Aspose.Words pro .NET, musíte do svého projektu importovat následující odkazy:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Otázka: Jak vytvořit nový dokument a generátor dokumentů v Aspose.Words pro .NET?

 Odpověď: Můžete vytvořit nový dokument pomocí`Document` třída a tvůrce dokumentů pomocí`DocumentBuilder`třída. Zde je příklad:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Dotaz: Jak vložit objekt OLE jako ikonu do dokumentu?

 Odpověď: Použijte Tvůrce dokumentů`InsertOleObjectAsIcon` metoda pro vložení objektu OLE jako ikony. Zadejte cestu k souboru OLE, příznak zobrazení, cestu k ikoně a název vloženého objektu. Zde je příklad:

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### Q. Jak uložit dokument s objektem OLE vloženým jako ikona?

 A: Použijte dokument`Save`způsob uložení dokumentu do souboru. Zde je příklad:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```