---
title: Hangsúlyok
linktitle: Hangsúlyok
second_title: Aspose.Words Document Processing API
description: Ismerje meg a kiemelések (félkövér és dőlt) használatát az Aspose.Words for .NET segítségével Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/emphases/
---

Ebben a példában elmagyarázzuk, hogyan használhatunk hangsúlyokat az Aspose.Words for .NET-hez. A kiemelések a szöveg bizonyos részei, például a félkövér és a dőlt betűk hangsúlyozására szolgálnak.

## 1. lépés: A dokumentum inicializálása

 Először is inicializáljuk a dokumentumot a példány létrehozásával`Document` osztály.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## 2. lépés: Dokumentumgenerátor használata

Ezután egy dokumentumgenerátort használunk, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Adjon hozzá szöveget hangsúlyokkal

A dokumentumgenerátor betűtípus tulajdonságainak módosításával kiemelő szöveget adhatunk hozzá. Ebben a példában félkövér és dőlt betűkkel hangsúlyozzuk a szöveg különböző részeit.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## 4. lépés: A dokumentum mentése

 Végül elmenthetjük a dokumentumot a kívánt formátumban. Ebben a példában a`.md` kiterjesztés egy Markdown formátumhoz.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Gratulálok ! Most már megtanulta, hogyan kell kiemeléseket használni az Aspose.Words for .NET segítségével.

### Példa az Emphases forráskódjához az Aspose.Words for .NET használatával


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### GYIK

#### K: Hogyan emelhetek ki szöveget a Markdown segítségével?

 V: A Markdown használatával szöveg kiemeléséhez egyszerűen vegye körül a szöveget a megfelelő szimbólumokkal. Használat`*` vagy`_` dőlt betűhöz,`**` vagy`__` merész, és`~~` az áthúzáshoz.

#### K: Kombinálhatunk-e különböző kiemeléseket ugyanabban a szövegben?

 V: Igen, lehetséges a különböző kiemelések kombinálása ugyanabban a szövegben. Például félkövér és dőlt betűvel szedhet egy szót, ha mindkettőt használja`**` és`*` szó körül.

#### K: Milyen kiemelési lehetőségek állnak rendelkezésre a Markdown alkalmazásban?

V: A Markdownban elérhető kiemelési lehetőségek dőlt (`*` vagy`_`), félkövér (`**` vagy`__`), és áthúzva (`~~`).

#### K: Hogyan kezelhetem azokat az eseteket, amikor a szöveg a Markdown által kiemelésre használt speciális karaktereket tartalmaz?

 V: Ha a szöveg speciális karaktereket tartalmaz, amelyeket a Markdown a kiemeléshez használ, kihagyhatja őket úgy, hogy megelőzi őket a karakterrel`\` . Például,`\*` szó szerinti csillagot jelenít meg.

#### K: Testreszabhatjuk a kiemelés megjelenését CSS használatával?

V: A Markdown kiemelése általában a böngésző alapértelmezett stílusait használja. Ha a Markdown-t HTML-re konvertálja, a CSS-szabályok segítségével testreszabhatja a kiemelések megjelenését.