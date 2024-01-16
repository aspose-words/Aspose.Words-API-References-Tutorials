---
title: Vložit Ole Objekt Do Wordu S Balíčkem Ole
linktitle: Vložit Ole Objekt Do Wordu S Balíčkem Ole
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak vložit objekt OLE s balíčkem OLE do dokumentu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Zde je podrobný návod k vysvětlení níže uvedeného zdrojového kódu C#, který ilustruje, jak vložit objekt OLE do aplikace Word s balíčkem OLE pomocí Aspose.Words for .NET.

## Krok 1: Importujte potřebné reference
Než začnete, ujistěte se, že jste do svého projektu naimportovali potřebné reference pro použití Aspose.Words for .NET. To zahrnuje import knihovny Aspose.Words a přidání požadovaných jmenných prostorů do zdrojového souboru.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Krok 2: Vytvořte nový dokument a generátor dokumentů
 V tomto kroku vytvoříme nový dokument pomocí`Document` třída a tvůrce dokumentů pomocí`DocumentBuilder` třída.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Vložte objekt OLE s balíčkem OLE
 Použijte generátor dokumentů`InsertOleObject` metoda pro vložení objektu OLE s balíčkem OLE do dokumentu. Zadejte datový proud, typ objektu, možnosti zobrazení a další nezbytná nastavení.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Krok 4: Uložte dokument
 Použijte dokument`Save` způsob uložení dokumentu do souboru.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Ukázkový zdrojový kód pro vložení objektu OLE s balíčkem OLE s Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Toto je kompletní ukázka kódu pro vložení objektu OLE s balíčkem OLE s Aspose.Words for .NET. Nezapomeňte importovat potřebné reference a postupujte podle výše popsaných kroků k integraci tohoto kódu do vašeho projektu.

## Závěr

Na závěr jsme prošli podrobným průvodcem vložení objektu OLE do dokumentu aplikace Word s balíčkem OLE pomocí Aspose.Words for .NET.

Podle těchto kroků budete moci úspěšně vkládat objekty OLE s balíčky OLE do dokumentů aplikace Word pomocí Aspose.Words for .NET. Nezapomeňte importovat potřebné reference a pečlivě dodržujte pokyny, abyste získali požadované výsledky.

### Časté dotazy pro vložení objektu ole do aplikace Word pomocí balíčku ole

#### Otázka: Jaké přihlašovací údaje musím importovat, abych mohl používat Aspose.Words pro .NET?

A: Chcete-li používat Aspose.Words pro .NET, musíte importovat následující odkazy:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### Otázka: Jak vytvořit nový dokument a generátor dokumentů?

 Odpověď: Můžete vytvořit nový dokument pomocí`Document` třída a tvůrce dokumentů pomocí`DocumentBuilder` třídy, jak je uvedeno níže:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Otázka: Jak vložit objekt OLE s balíčkem OLE do dokumentu?

 A: Použijte`InsertOleObject`metoda tvůrce dokumentů (`DocumentBuilder`) pro vložení objektu OLE s balíkem OLE do dokumentu. Zadejte datový proud, typ objektu, možnosti zobrazení a další nezbytná nastavení. Zde je příklad:

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### Otázka: Jak uložit dokument?

 A: Použijte dokument`Save` způsob uložení dokumentu do souboru. Zde je příklad:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### Otázka: Můžete poskytnout úplný příklad vložení objektu OLE s balíčkem OLE s Aspose.Words for .NET?

Odpověď: Zde je úplný ukázkový kód pro vložení objektu OLE s balíčkem OLE pomocí Aspose.Words for .NET. Nezapomeňte importovat potřebné reference a postupujte podle výše popsaných kroků k integraci tohoto kódu do vašeho projektu:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

Tímto končí náš tutoriál o vložení objektu OLE s balíčkem OLE do dokumentu aplikace Word pomocí Aspose.Words for .NET. Neváhejte importovat potřebné reference a postupujte podle popsaných kroků k integraci tohoto kódu do vašeho projektu. Máte-li jakékoli další dotazy, neváhejte nás kontaktovat.