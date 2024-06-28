---
title: Přijmout recenze
linktitle: Přijmout recenze
second_title: Aspose.Words API pro zpracování dokumentů
description: Naučte se přijímat revize dokumentu aplikace Word pomocí Aspose.Words for .NET
type: docs
weight: 10
url: /cs/net/working-with-revisions/accept-revisions/
---

V tomto tutoriálu vás provedeme přijímáním revizí dokumentu aplikace Word pomocí funkce Přijmout revize Aspose.Words for .NET. Chcete-li porozumět zdrojovému kódu a přijmout změny v dokumentu, postupujte podle následujících kroků.

## Krok 1: Přidání a úprava obsahu dokumentu

V tomto příkladu vytváříme dokument a přidáváme obsah. Pro ilustraci změn a revizí používáme několik odstavců. Zde je postup:

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Přidejte text do prvního odstavce a poté přidejte další dva odstavce.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Krok 2: Sledujte recenze a přidejte recenze

Umožňujeme sledování revizí a přidáváme revizi do dokumentu. Zde je postup:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Tento odstavec je revizí a bude mít nastaven odpovídající příznak "IsInsertRevision".
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Krok 3: Odstraňte odstavec a spravujte revize

Odstraníme odstavec a zkontrolujeme uložené revize. Zde je postup:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Jak sledujeme revize, odstavec v dokumentu stále existuje, bude mít nastaven příznak "IsDeleteRevision"
// a bude se zobrazovat jako recenze v aplikaci Microsoft Word, dokud nepřijmeme nebo neodmítneme všechny recenze.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Krok 4: Přijměte změny

Přijímáme všechny změny dokumentu. Zde je postup:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Krok 5: Zastavte sledování recenzí

Přestaneme sledovat revize, aby se změny v dokumentu již nezobrazovaly jako revize. Zde je postup:

```csharp
doc.StopTrackRevisions();
```
## Krok 6: Uložení dokumentu

 Po vložení pole formuláře pro zadání textu uložte dokument na požadované místo pomocí`Save` metoda. Ujistěte se, že jste zadali správnou cestu k souboru:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Příklad zdrojového kódu pro Accept Revisions using Aspose.Words for .NET

Zde je úplný zdrojový kód pro přijímání změn v dokumentu pomocí Aspose.Words pro .NET:


```csharp
// Cesta k adresáři dokumentů.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Přidejte text do prvního odstavce a poté přidejte další dva odstavce.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//Máme tři odstavce, z nichž žádný není registrován jako jakýkoli typ revize
// Pokud při sledování revizí přidáme/odebereme jakýkoli obsah v dokumentu,
// budou jako takové zobrazeny v dokumentu a lze je přijmout/odmítnout.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Tento odstavec je revizí a bude mít nastavený příznak "IsInsertRevision".
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Získejte kolekci odstavců dokumentu a odstraňte odstavec.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Protože sledujeme revize, odstavec v dokumentu stále existuje, bude mít nastaveno "IsDeleteRevision"
// a budou zobrazeny jako revize v aplikaci Microsoft Word, dokud nepřijmeme nebo neodmítneme všechny revize.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Smazaný odstavec revize je odstraněn, jakmile přijmeme změny.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Zastavení sledování revizí způsobí, že se tento text zobrazí jako normální text.
// Při změně dokumentu se revize nepočítají.
doc.StopTrackRevisions();

// Uložte dokument.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Závěr

V tomto tutoriálu jsme se naučili, jak přijímat revize v dokumentu aplikace Word pomocí funkce Přijmout revize Aspose.Words for .NET. Postupovali jsme podle kroků pro přidání a úpravu obsahu dokumentu, sledování revizí, odstranění revidovaného odstavce, přijetí všech změn a zastavení sledování revizí. Nyní můžete tyto znalosti použít k efektivní správě revizí ve vašich vlastních dokumentech aplikace Word pomocí Aspose.Words for .NET.

### Nejčastější dotazy

#### Otázka: Jak povolím sledování revizí v Aspose.Words pro .NET?

#### Řešení 1:

 A: Chcete-li povolit sledování revizí v Aspose.Words pro .NET, použijte`StartTrackRevisions` metoda`Document` objekt a zadejte jméno autora a počáteční datum pro sledování revize.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Řešení 2:

 Odpověď: Můžete také povolit sledování revizí pomocí`Document` konstruktor, který přijímá`trackRevisions` a`author` parametry.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### Otázka: Jak přijmout všechny změny v dokumentu pomocí Aspose.Words for .NET?

 A: Použijte`AcceptAllRevisions` metoda`Document` zamítnout přijmout všechny změny provedené v dokumentu.

```csharp
doc.AcceptAllRevisions();
```

#### Otázka: Jak uložím upravený dokument s přijatými revizemi?

 Použijte`Save` metoda`Document` objekt pro uložení upraveného dokumentu s přijatými revizemi. Ujistěte se, že jste zadali správnou cestu k souboru.

```csharp
doc.Save("path/to/the/document.docx");
```

#### Otázka: Jak zastavím sledování revizí v Aspose.Words pro .NET?

 A: Použijte`StopTrackRevisions` metoda`Document` objekt k zastavení revizí sledování.

```csharp
doc.StopTrackRevisions();
```

#### Otázka: Jak odstraním revidovaný odstavec v dokumentu pomocí Aspose.Words for .NET?

 A: Chcete-li odstranit revidovaný odstavec v dokumentu, můžete použít`Remove` metoda sběru odstavců.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```