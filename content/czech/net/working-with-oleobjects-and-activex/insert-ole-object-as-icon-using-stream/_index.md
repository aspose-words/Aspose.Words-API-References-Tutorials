---
title: Vložit OLE objekt jako ikonu pomocí proudu
linktitle: Vložit OLE objekt jako ikonu pomocí proudu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se vložit objekt OLE jako ikonu pomocí streamu pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Zde je krok za krokem vysvětlující zdrojový kód C# níže, který ilustruje, jak vložit objekt OLE jako ikonu pomocí streamu s Aspose.Words for .NET.

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

## Krok 3: Vložte objekt OLE jako ikonu ze streamu
 Použijte Tvůrce dokumentů`InsertOleObjectAsIcon` metoda pro vložení objektu OLE jako ikony z proudu do dokumentu. Zadejte datový proud, typ objektu, cestu k ikoně a název vloženého objektu.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Krok 4: Uložte dokument
 Použijte dokument`Save` způsob uložení dokumentu do souboru.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Příklad zdrojového kódu pro vložení objektu OLE jako ikony pomocí streamu s Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

Toto je kompletní ukázka kódu pro vložení objektu OLE jako ikony pomocí streamu s Aspose.Words for .NET. Nezapomeňte importovat potřebné reference a postupujte podle výše popsaných kroků k integraci tohoto kódu do vašeho projektu.

## Závěr

Výše uvedený podrobný průvodce vysvětluje, jak vložit objekt OLE jako ikonu do dokumentu aplikace Word pomocí toku s Aspose.Words for .NET. Podle popsaných kroků budete moci integrovat tuto funkci do svého projektu. Nezapomeňte importovat potřebné reference, vytvořit nový dokument a generátor dokumentů, vložit objekt OLE jako ikonu ze streamu a poté dokument uložit. Jako výchozí bod použijte poskytnutý ukázkový kód a přizpůsobte jej svým potřebám.

### FAQ

#### Otázka: Jak importovat potřebné odkazy pro použití Aspose.Words pro .NET?

A. Chcete-li importovat potřebné reference, musíte provést následující kroky:

 Přidejte následující`using` příkazy v horní části zdrojového souboru:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Ujistěte se, že jste do projektu přidali knihovnu Aspose.Words.

#### Otázka: Jak vytvořit nový dokument a tvůrce dokumentů pomocí Aspose.Words for .NET?

A. Chcete-li vytvořit nový dokument a generátor dokumentů, postupujte takto:

 Použijte`Document` třídy k vytvoření nového dokumentu:

```csharp
Document doc = new Document();
```
 Použijte`DocumentBuilder`třídy k vytvoření tvůrce dokumentů přidruženého k dříve vytvořenému dokumentu:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Otázka: Jak vložit objekt OLE jako ikonu ze streamu pomocí Aspose.Words for .NET?

A. Chcete-li vložit objekt OLE jako ikonu ze streamu, postupujte takto:

 Použijte`InsertOleObjectAsIcon` metoda generátoru dokumentů pro vložení objektu OLE:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### Otázka: Jak uložit dokument do souboru?

A.  Chcete-li dokument uložit do souboru, můžete použít`Save` metoda dokumentu určující cílovou cestu:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### Dotaz: Jak mohu vložit kód pro vložení objektu OLE jako ikonu z proudu do mého projektu?

A. Chcete-li do projektu vložit kód pro vložení objektu OLE jako ikonu ze streamu, postupujte takto:
-  Importujte potřebné reference přidáním příslušných`using` prohlášení.
-  Vytvořte nový dokument a tvůrce dokumentů pomocí`Document` a`DocumentBuilder` třídy.
- Použijte kód pro vložení objektu OLE jako ikonu ze streamu.
-  Uložte dokument pomocí`Save` metoda s příslušnou cílovou cestou.

Podle těchto kroků budete moci úspěšně vložit objekt OLE jako ikonu ze streamu pomocí Aspose.Words for .NET. Ujistěte se, že postupujte podle pokynů a importujte potřebné reference, abyste získali požadované výsledky.