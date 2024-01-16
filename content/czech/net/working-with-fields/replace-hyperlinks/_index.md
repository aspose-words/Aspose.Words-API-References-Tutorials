---
title: Nahradit hypertextové odkazy
linktitle: Nahradit hypertextové odkazy
second_title: Aspose.Words API pro zpracování dokumentů
description: Nahraďte hypertextové odkazy v dokumentech aplikace Word pomocí Aspose.Words for .NET. Podrobné pokyny pro nahrazení hypertextových odkazů.
type: docs
weight: 10
url: /cs/net/working-with-fields/replace-hyperlinks/
---

Zde je podrobný průvodce, který vysvětluje následující zdrojový kód jazyka C#, který nahrazuje hypertextové odkazy pomocí funkce Aspose.Words for .NET. Před použitím tohoto kódu se ujistěte, že jste do projektu zahrnuli knihovnu Aspose.Words.

## Krok 1: Nastavte cestu k adresáři dokumentu

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Ujistěte se, že jste zadali správnou cestu k adresáři dokumentů obsahujícímu`Hyperlinks.docx` soubor.

## Krok 2: Načtěte dokument obsahující hypertextové odkazy

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Zde vytváříme instanci`Document` třídy ze zadaného souboru.

## Krok 3: Procházením polí vyhledejte hypertextové odkazy

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Některé hypertextové odkazy mohou být lokální (odkazy na záložky uvnitř dokumentu), ignorujeme je.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Tato smyčka prochází všemi poli v dokumentu a hledá pole typu`FieldType.FieldHyperlink` . Jakmile je pole tohoto typu nalezeno, zkontrolujeme, zda se jedná o místní odkaz zaškrtnutím`SubAddress` vlastnictví. Pokud ne, nahradíme adresu odkazu`"http://www.aspose.com"` a výsledek s`"Aspose - The .NET & Java Component Editor"`.

## Krok 4: Uložte upravený dokument

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Nakonec upravený dokument s nahrazenými hypertextovými odkazy uložíme do určeného souboru.

### Příklad zdrojového kódu pro nahrazení hypertextových odkazů Aspose.Words pro .NET

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Některé hypertextové odkazy mohou být lokální (odkazy na záložky uvnitř dokumentu), ignorujeme je.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Toto je ukázkový zdrojový kód pro nahrazení hypertextových odkazů v dokumentu pomocí Aspose.Words for .NET.

### FAQ

#### Otázka: Jak mohu nahradit hypertextové odkazy v dokumentu aplikace Word pomocí Aspose.Words for .NET?

 Odpověď: Chcete-li nahradit hypertextové odkazy v dokumentu aplikace Word pomocí Aspose.Words for .NET, můžete použít`Document.Range.Replace`metoda určující text, který se má hledat, a nahrazující text. Ujistěte se, že používáte příslušné možnosti pro nastavení parametrů vyhledávání a nahrazování.

#### Otázka: Je možné nahradit Aspose.Words for .NET pouze určité hypertextové odkazy v dokumentu aplikace Word?

Odpověď: Ano, je možné nahradit pouze určité hypertextové odkazy v dokumentu aplikace Word pomocí Aspose.Words for .NET. Hypertextové odkazy, které mají být nahrazeny, můžete filtrovat pomocí specifických kritérií, jako je adresa URL odkazu, text odkazu nebo jakákoli jiná relevantní vlastnost. Poté můžete použít náhradu pouze na odpovídající hypertextové odkazy.

#### Otázka: Jak mohu ignorovat hypertextové odkazy v záhlaví, zápatí nebo poznámkách pod čarou při nahrazení Aspose.Words pro .NET?

Odpověď: Chcete-li ignorovat hypertextové odkazy v záhlaví, zápatí nebo poznámkách pod čarou při nahrazení Aspose.Words pro .NET, můžete použít rozšířené možnosti vyhledávání a zadat příslušné limity vyhledávání. Můžete například omezit hledání na hlavní části dokumentu a vyloučit záhlaví, zápatí nebo poznámky pod čarou.

#### Otázka: Je možné nahradit hypertextové odkazy interními odkazy na jiné části dokumentu?

 Odpověď: Ano, je možné nahradit hypertextové odkazy interními odkazy na jiné části dokumentu pomocí Aspose.Words for .NET. Můžete použít kotvy nebo textová id k vytvoření interních odkazů a poté je nahradit pomocí`Document.Range.Replace` metoda s příslušnými možnostmi.

#### Otázka: Zachová nahrazení hypertextových odkazů pomocí Aspose.Words for .NET vlastnosti odkazu, jako jsou barvy nebo styly?

Odpověď: Ano, při nahrazení hypertextových odkazů pomocí Aspose.Words for .NET se zachovají vlastnosti odkazu, jako jsou barvy nebo styly. Chcete-li dosáhnout konzistentního výsledku, můžete zadat stejné vlastnosti formátování v nahrazovaném textu.