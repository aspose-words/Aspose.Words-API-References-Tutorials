---
title: Megjegyzések eltávolítása a PDF fájlból
linktitle: Megjegyzések eltávolítása a PDF fájlból
second_title: Aspose.Words Document Processing API
description: Távolítsa el a megjegyzéseket egy PDF-fájlból az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-revisions/remove-comments-in-pdf/
---

Ebben a lépésenkénti útmutatóban bemutatjuk, hogyan távolíthat el megjegyzéseket egy PDF-fájlból az Aspose.Words for .NET segítségével. Megadjuk Önnek a teljes forráskódot, és megmutatjuk, hogyan kell formázni a markdown kimenetet.

## 1. lépés: A dokumentum betöltése

Az első lépés a megjegyzéseket tartalmazó dokumentum betöltése.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 2. lépés: Megjegyzések elrejtése PDF-ben

Az elrendezési beállítást úgy konfiguráljuk, hogy elrejtse a megjegyzéseket a PDF létrehozásakor.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## 3. lépés: Mentse el a dokumentumot PDF formátumban

Végül a megjegyzések törlésével PDF formátumban mentjük el a dokumentumot.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Markdown kimeneti formátumok

Az olvashatóság javítása érdekében a kimenet markdown-ban formázható. Például :

```markdown
- Comments are hidden in the generated PDF.
```

### Példa forráskód a megjegyzések eltávolításához PDF-ben az Aspose.Words for .NET használatával

Itt található a teljes forráskód a megjegyzések eltávolításához egy PDF-fájlból az Aspose.Words for .NET használatával:

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Megjegyzések elrejtése a PDF-ben.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan távolíthat el megjegyzéseket egy PDF-fájlból az Aspose.Words for .NET segítségével. A megfelelő elrendezési lehetőségek használatával el tudtuk rejteni a megjegyzéseket a PDF generálásakor. Az Aspose.Words for .NET nagy rugalmasságot kínál a Word-fájlok kezeléséhez és különböző formátumokká konvertálásához, beleértve a PDF-formátumokat is. Ezt a tudást most már használhatja megjegyzések eltávolítására saját PDF-fájljaiból az Aspose.Words for .NET segítségével.

### GYIK a megjegyzések eltávolításához pdf fájlban

#### K: Hogyan lehet dokumentumot feltölteni az Aspose.Words for .NET-be?

 V: Használja a`Document` osztályú Aspose.Words .NET-hez a dokumentum fájlból való betöltéséhez. Megadhatja a teljes dokumentum elérési utat.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### K: Hogyan lehet elrejteni a megjegyzéseket az Aspose.Words for .NET segítségével generált PDF-ben?

 V: Használja a`CommentDisplayMode` tulajdona a`LayoutOptions` objektum a megjegyzések megjelenítési módjának konfigurálásához a PDF generálásakor. A megjegyzések elrejtéséhez állítsa be ezt a tulajdonságot`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### K: Hogyan lehet dokumentumot PDF formátumban menteni az Aspose.Words for .NET segítségével?

 V: Használja a`Save` módszere a`Document` objektumot a dokumentum PDF formátumban történő mentéséhez. Adja meg a PDF-fájl teljes elérési útját.

```csharp
doc.Save("path/to/the/file.pdf");
```