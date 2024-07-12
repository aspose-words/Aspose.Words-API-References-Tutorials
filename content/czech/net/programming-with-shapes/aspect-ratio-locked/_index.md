---
title: Poměr stran uzamčen
linktitle: Poměr stran uzamčen
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se zamknout nebo odemknout poměr stran tvaru v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-shapes/aspect-ratio-locked/
---

Tento tutoriál vysvětluje, jak zamknout nebo odemknout poměr stran tvaru v dokumentu aplikace Word pomocí Aspose.Words for .NET. Uzamčením poměru stran můžete zachovat původní proporce tvaru při změně jeho velikosti.

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

## Krok 3: Vložte obrazový tvar
 Použijte`InsertImage` metoda`DocumentBuilder`objekt pro vložení tvaru obrázku do dokumentu. Jako parametr zadejte cestu k souboru obrázku.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Krok 4: Zamkněte nebo odemkněte poměr stran
 Nastav`AspectRatioLocked` vlastnost tvaru k`true` nebo`false` pro zamknutí nebo odemknutí poměru stran, resp.

```csharp
shape.AspectRatioLocked = false; // Odemkněte poměr stran
```

## Krok 5: Uložte dokument
 Uložte dokument do určeného adresáře pomocí`Save` metoda. Zadejte požadovaný název souboru s příslušnou příponou souboru. V tomto příkladu dokument uložíme jako „WorkingWithShapes.AspectRatioLocked.docx“.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Příklad zdrojového kódu pro poměr stran uzamčen pomocí Aspose.Words pro .NET 

```csharp
	// Cesta k vašemu adresáři dokumentů
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

A je to! Úspěšně jste uzamkli nebo odemkli poměr stran obrazce v dokumentu aplikace Word pomocí Aspose.Words for .NET.