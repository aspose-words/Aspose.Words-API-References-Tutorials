---
title: Přidat rohy ustřižené
linktitle: Přidat rohy ustřižené
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak přidat tvar s oříznutými rohy do dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-shapes/add-corners-snipped/
---

 Tento tutoriál vysvětluje, jak přidat tvar s vystřiženými rohy do dokumentu aplikace Word pomocí Aspose.Words for .NET. Tvar odříznutých rohů lze přizpůsobit a vložit pomocí`InsertShape` metoda.

## Předpoklady
Abyste mohli postupovat podle tohoto návodu, musíte mít následující:

- Nainstalovaná knihovna Aspose.Words for .NET.
- Základní znalost C# a Word Processing s dokumenty Word.

## Krok 1: Nastavte adresář dokumentů
 Začněte nastavením cesty k adresáři dokumentů. Nahradit`"YOUR DOCUMENT DIRECTORY"`se skutečnou cestou k adresáři, kam chcete dokument uložit.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Krok 2: Vytvořte nový dokument a DocumentBuilder
 Vytvořte novou instanci souboru`Document` třída a a`DocumentBuilder` objekt pracovat s dokumentem.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Krok 3: Vložte tvar s odříznutými rohy
 Použijte`InsertShape` metoda`DocumentBuilder` objekt pro vložení tvaru s odříznutými rohy. Zadejte typ tvaru (v tomto případě`ShapeType.TopCornersSnipped`) a zadejte požadovanou velikost tvaru.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Krok 4: Uložte dokument
 Uložte dokument do určeného adresáře pomocí`Save`metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu dokument uložíme jako „WorkingWithShapes.AddCornersSnipped.docx“.

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Příklad zdrojového kódu pro Add Corners Snipped pomocí Aspose.Words for .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

A je to! Úspěšně jste do dokumentu aplikace Word pomocí Aspose.Words pro .NET přidali tvar s odříznutými rohy.