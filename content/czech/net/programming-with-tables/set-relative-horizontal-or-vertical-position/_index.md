---
title: Nastavte relativní horizontální nebo vertikální polohu
linktitle: Nastavte relativní horizontální nebo vertikální polohu
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se, jak nastavit relativní vodorovnou nebo svislou polohu tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET.
type: docs
weight: 10
url: /cs/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

V tomto tutoriálu se naučíme, jak nastavit relativní horizontální nebo vertikální polohu tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Budeme postupovat podle průvodce krok za krokem, abychom porozuměli kódu a implementovali tuto funkci. Na konci tohoto kurzu budete schopni nastavit relativní vodorovnou nebo svislou polohu tabulky v dokumentech aplikace Word.

## Krok 1: Nastavení projektu
1. Spusťte Visual Studio a vytvořte nový projekt C#.
2. Přidejte odkaz na knihovnu Aspose.Words for .NET.

## Krok 2: Načtení dokumentu
Chcete-li spustit textový editor s dokumentem, postupujte takto:

```csharp
// Cesta k adresáři vašich dokumentů
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Vložte dokument
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Nezapomeňte nahradit „VAŠE ADRESÁŘ DOKUMENTŮ“ skutečnou cestou k adresáři vašich dokumentů a uveďte správný název souboru.

## Krok 3: Nastavení relativní polohy stolu
Dále nastavíme relativní horizontální nebo vertikální polohu stolu. Použijte následující kód:

```csharp
// Získejte tabulku
Table table = doc.FirstSection.Body.Tables[0];

//Definice relativní vodorovné polohy stolu
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Definujte relativní vertikální polohu stolu
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Zde použijeme dokument k načtení první tabulky z těla první sekce. Dále nastavíme relativní vodorovnou polohu stolu pomocí`HorizontalAnchor` nemovitost pomocí`RelativeHorizontalPosition.Column` hodnota. Podobně nastavíme relativní vertikální polohu stolu pomocí`VerticalAnchor` nemovitost pomocí`RelativeVerticalPosition.Page` hodnota.

## Krok 4: Uložení upraveného dokumentu
Nakonec musíme upravený dokument uložit s definovanou relativní pozicí tabulky. Použijte následující kód:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Nezapomeňte zadat správnou cestu a název souboru pro výstupní dokument.

### Ukázkový zdrojový kód pro nastavení relativní horizontální nebo vertikální polohy pomocí Aspose.Words pro .NET 

```csharp
// Cesta k vašemu adresáři dokumentů
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Závěr
V tomto tutoriálu jsme se naučili, jak nastavit relativní horizontální nebo vertikální polohu tabulky v dokumentu aplikace Word pomocí Aspose.Words for .NET. Podle tohoto podrobného průvodce a implementace poskytnutého kódu C# můžete tuto relativní pozici použít na tabulky v dokumentech aplikace Word.