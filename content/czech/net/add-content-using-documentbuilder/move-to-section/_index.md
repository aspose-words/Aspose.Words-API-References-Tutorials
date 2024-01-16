---
title: Přesunout do oddílu v dokumentu aplikace Word
linktitle: Přesunout do oddílu v dokumentu aplikace Word
second_title: Aspose.Words API pro zpracování dokumentů
description: Podrobný průvodce používáním funkce Přesunout do oddílu v dokumentu aplikace Word funkce Aspose.Words for .NET manipulovat s oddíly a odstavci v dokumentech aplikace Word.
type: docs
weight: 10
url: /cs/net/add-content-using-documentbuilder/move-to-section/
---
V tomto příkladu vás krok za krokem provedeme pomocí dodaného zdrojového kódu C# pomocí funkce Přesunout do oddílu v dokumentu aplikace Word aplikace Aspose.Words for .NET. Tato funkce vám umožňuje procházet a manipulovat s různými sekcemi v dokumentu aplikace Word. Pro integraci této funkce do vaší aplikace postupujte podle následujících kroků.

## Krok 1: Vytvořte nový dokument a přidejte sekci

Nejprve musíme vytvořit nový dokument a přidat do něj sekci. K provedení tohoto kroku použijte následující kód:

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));
```

Tento kód vytvoří nový prázdný dokument a přidá do tohoto dokumentu sekci.

## Krok 2: Přesuňte DocumentBuilder do druhé části a přidejte text

Dále musíme přesunout DocumentBuilder do druhé části dokumentu a přidat tam nějaký text. K provedení tohoto kroku použijte následující kód:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");
```

Tento kód vytvoří DocumentBuilder ze stávajícího dokumentu a poté přesune kurzor z DocumentBuilder do druhé části dokumentu. Nakonec do této sekce přidá zadaný text.

## Krok 3: Načtěte dokument s existujícími odstavci

Pokud chcete pracovat s existujícím dokumentem obsahujícím odstavce, můžete tento dokument načíst pomocí následujícího kódu:

```csharp
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);
```

Tento kód načte zadaný dokument (nahraďte "MyDir + "Paragraphs.docx"" se skutečnou cestou k vašemu dokumentu) a přistupuje ke kolekci odstavců z první části dokumentu. Linie`Assert.AreEqual(22, paragraphs.Count);` kontroluje, zda dokument obsahuje 22 odstavců.

## Krok 4: Vytvořte DocumentBuilder pro dokument

Kurzor DocumentBuilderu můžete vytvořit na konkrétní odstavec pomocí pozičních indexů.

```csharp
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));
```

## Krok 5: Přesuňte kurzor na konkrétní odstavec


Kurzor DocumentBuilderu můžete přesunout na konkrétní odstavec pomocí pozičních indexů. Jak na to:

```csharp
builder. MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph.");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

Tento kód přesune kurzor DocumentBuilderu do třetího odstavce druhé sekce (odstavec na indexu 2) a na pozici 10. Poté přidá nový odstavec s nějakým textem a zkontroluje, zda je kurzor na tomto novém odstavci dobře umístěn.

### Příklad zdrojového kódu pro Move To Move To Section pomocí Aspose.Words for .NET

```csharp
Document doc = new Document();
doc.AppendChild(new Section(doc));

// Přesuňte DocumentBuilder do druhé sekce a přidejte text.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToSection(1);
builder.Writeln("Text added to the 2nd section.");

// Vytvořte dokument s odstavci.
doc = new Document(MyDir + "Paragraphs.docx");
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual(22, paragraphs.Count);

// Když vytvoříme DocumentBuilder pro dokument, jeho kurzor je ve výchozím nastavení na samém začátku dokumentu,
// a veškerý obsah přidaný pomocí DocumentBuilder bude pouze připojen k dokumentu.
builder = new DocumentBuilder(doc);
Assert.AreEqual(0, paragraphs.IndexOf(builder.CurrentParagraph));

//Kurzor můžete přesunout na libovolné místo v odstavci.
builder.MoveToParagraph(2, 10);
Assert.AreEqual(2, paragraphs.IndexOf(builder.CurrentParagraph));
builder.Writeln("This is a new third paragraph. ");
Assert.AreEqual(3, paragraphs.IndexOf(builder.CurrentParagraph));
```

To je vše ! Nyní jste pochopili, jak používat funkci přechodu do sekce Aspose.Words for .NET pomocí poskytnutého zdrojového kódu. Nyní můžete tuto funkci integrovat do své vlastní aplikace a dynamicky manipulovat s oddíly a odstavci dokumentů aplikace Word.

## Závěr

V tomto příkladu jsme prozkoumali funkci Přesunout do sekce Aspose.Words pro .NET. Naučili jsme se, jak vytvořit nový dokument, přidat do něj oddíly a použít třídu DocumentBuilder k navigaci do konkrétních oddílů a odstavců v dokumentu aplikace Word. Tato funkce poskytuje vývojářům výkonné nástroje pro manipulaci s obsahem a strukturou dokumentů aplikace Word programově pomocí Aspose.Words for .NET.

### Časté dotazy pro přesun do sekce v dokumentu aplikace Word

#### Otázka: Jaký je účel funkce Přesunout do sekce v Aspose.Words pro .NET?

Odpověď: Funkce Přesunout do oddílu v Aspose.Words for .NET umožňuje vývojářům programově procházet a manipulovat s různými oddíly v dokumentu Wordu. Poskytuje možnost vkládat, upravovat nebo odstraňovat obsah v určitých částech dokumentu.

#### Otázka: Jak přesunu DocumentBuilder do určité sekce v dokumentu aplikace Word?

Odpověď: Chcete-li přesunout DocumentBuilder do určité sekce v dokumentu aplikace Word, můžete použít metodu MoveToSection třídy DocumentBuilder. Tato metoda bere jako parametr index cílové sekce a umístí kurzor na začátek této sekce.

#### Otázka: Mohu přidat nebo upravit obsah po přesunutí do konkrétní sekce pomocí funkce Přesunout do sekce?

Odpověď: Ano, jakmile je DocumentBuilder umístěn do požadované sekce pomocí MoveToSection, můžete použít různé metody třídy DocumentBuilder, jako je Writeln, Write nebo InsertHtml, abyste přidali nebo upravili obsah této sekce.

#### Otázka: Jak mohu pracovat s existujícími odstavci v dokumentu pomocí funkce Přesunout do oddílu?

Odpověď: Můžete načíst existující dokument obsahující odstavce pomocí konstruktoru dokumentu a poté získat přístup ke kolekci odstavců z požadované sekce pomocí vlastnosti FirstSection.Body.Paragraphs.

#### Otázka: Mohu přesunout kurzor DocumentBuilderu na konkrétní odstavec v sekci pomocí funkce Přesunout do sekce?

Odpověď: Ano, můžete přesunout kurzor DocumentBuilderu na konkrétní odstavec v sekci pomocí metody MoveToParagraph. Tato metoda bere jako parametry indexy cílového odstavce a pozici znaku (offset) v odstavci.