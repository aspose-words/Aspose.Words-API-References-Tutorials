---
title: Vložit pole TOA bez Tvůrce dokumentů
linktitle: Vložit pole TOA bez Tvůrce dokumentů
second_title: Aspose.Words API pro zpracování dokumentů
description: Průvodce krok za krokem pro vložení pole TOA bez Tvůrce dokumentů pomocí Aspose.Words pro .NET.
type: docs
weight: 10
url: /cs/net/working-with-fields/insert-toafield-without-document-builder/
---

Zde je podrobný návod k vysvětlení zdrojového kódu C# níže, který používá funkci "TOA Field Insertion" Aspose.Words for .NET. Pečlivě dodržujte každý krok, abyste dosáhli požadovaných výsledků.

## Krok 1: Nastavení adresáře dokumentů

V poskytnutém kódu musíte zadat adresář vašich dokumentů. Nahraďte hodnotu „VÁŠ ADRESÁŘ DOKUMENTŮ“ příslušnou cestou k adresáři vašich dokumentů.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Krok 2: Vytvoření dokumentu a odstavce

Začneme vytvořením nového dokumentu a inicializací odstavce.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Krok 3: Vložení pole TA

Pro vložení pole TA do odstavce používáme třídu FieldTA.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Krok 4: Přidání odstavce do těla dokumentu

Do těla dokumentu přidáme odstavec obsahující pole TA.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Krok 5: Vytvoření odstavce pro pole TOA

Vytvoříme nový odstavec pro pole TOA.

```csharp
para = new Paragraph(doc);
```

## Krok 6: Vložení pole TOA

Pro vložení pole TOA do odstavce používáme třídu FieldToa.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Krok 7: Přidání odstavce do těla dokumentu

Do těla dokumentu přidáme odstavec obsahující pole TOA.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Krok 8: Aktualizujte pole TOA

 Nakonec zavoláme`Update()` způsob aktualizace pole TOA.

```csharp
fieldToa.Update();
```

### Příklad zdrojového kódu pro vkládání pole TOA bez Tvůrce dokumentů s Aspose.Words pro .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Chceme vložit pole TA a TOA takto:
// { TA \c 1 \l "Hodnota 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### FAQ

#### Otázka: Jak upravit vzhled pole TOA vloženého do dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Vzhled vloženého pole TOA můžete přizpůsobit pomocí vlastností`FieldTOA` objekt k určení možností formátování.

#### Otázka: Mohu přidat více polí TOA do jednoho dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Ano, můžete přidat více polí TOA do jednoho dokumentu aplikace Word pomocí Aspose.Words for .NET. Stačí opakovat kroky vložení pro každé pole.

#### Otázka: Jak mohu zkontrolovat, zda bylo pole TOA úspěšně vloženo do dokumentu aplikace Word pomocí Aspose.Words for .NET?

Odpověď: Chcete-li zkontrolovat, zda bylo pole TOA úspěšně vloženo, můžete procházet obsah dokumentu a hledat instance pole TOA.

#### Otázka: Má vložení pole TOA bez použití DocumentBuilder vliv na formátování dokumentu Word pomocí Aspose.Words for .NET?

Odpověď: Vložení pole TOA bez použití DocumentBuilder neovlivňuje přímo formátování dokumentu aplikace Word. Možnosti formátování pole TOA však mohou ovlivnit celkové formátování dokumentu.