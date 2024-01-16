---
title: Figyelmeztetési forrás használata
linktitle: Figyelmeztetési forrás használata
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan használhatja a figyelmeztető forrást az Aspose.Words for .NET-hez Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/use-warning-source/
---

Ebben a példában bemutatjuk, hogyan használhatja a figyelmeztető forrást az Aspose.Words for .NET-hez. A figyelmeztetés forrása jelzi a figyelmeztetés eredetét a visszahívási funkció használatakor.

## 1. lépés: A dokumentum betöltése

 Egy meglévő, figyelmeztetéseket tartalmazó dokumentumot töltünk be a`Load` módszere a`Document` osztály.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## 3. lépés: A figyelmeztető forrás használata

 A figyelmeztetés forrását a dokumentum beállításával fogjuk használni`WarningCallback` ingatlan gyűjteményébe`WarningInfo` tárgyakat.

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## 4. lépés: A dokumentum mentése

Végül elmenthetjük a dokumentumot a kívánt formátumban.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### Példa forráskódra a figyelmeztető forrás használatához az Aspose.Words .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

Gratulálok ! Most megtanulta, hogyan kell használni a figyelmeztető forrást az Aspose.Words for .NET-hez.

### GYIK

#### K: Testreszabhatjuk a "Figyelmeztetés" címke megjelenését?

 V: A "Warning" címke formázása a használt Markdown renderertől függ. A legtöbb esetben testreszabhatja a megjelenést a CSS használatával a célzáshoz`blockquote` címkét a dokumentumban.

#### K: Lehetséges ikonokat hozzáadni a "Figyelmeztetés" címkéhez?

V: Igen, lehetőség van ikonok hozzáadására a „Figyelmeztetés” címkéhez a Markdown dokumentumban található HTML-kód használatával. Beillesztheti a`span` címkével a megfelelő osztályt, hogy egy ikon jelenjen meg a figyelmeztető szöveg mellett.

#### K: A "Warning" címke kompatibilis az összes Markdown olvasóval?

 V: A "Warning" címke kompatibilitása a használt Markdown megjelenítéstől függ. A legtöbb Markdown olvasó támogatja a`blockquote` címke a kiemelt szöveg megjelenítéséhez, de a pontos megjelenés változhat.