---
title: Mértékegység
linktitle: Mértékegység
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan adhatja meg a mértékegységet egy Word-dokumentum ODT-re konvertálásakor az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-odtsaveoptions/measure-unit/
---

Amikor egy Word dokumentumot OpenDocument Text (ODT) formátumba konvertál egy C# alkalmazásban, érdemes lehet megadni a mérhető formázáshoz és tartalomtulajdonságokhoz használt mértékegységet. A .NET Aspose.Words könyvtárával egyszerűen megadhatja ezt a funkciót az OdtSaveOptions mentési beállításaival. Ebben a részletes útmutatóban végigvezetjük, hogyan használhatja az Aspose.Words for .NET C# forráskódot Word-dokumentumok ODT-re való konvertálásához az OdtSaveOptions segítségével a mértékegység megadásával.

## Az Aspose.Words könyvtár megértése

Mielőtt belemerülne a kódba, fontos megérteni a .NET Aspose.Words könyvtárát. Az Aspose.Words egy hatékony könyvtár Word dokumentumok létrehozásához, szerkesztéséhez, konvertálásához és védelméhez különböző platformokon, beleértve a .NET-et is. Számos funkciót kínál a dokumentumok kezeléséhez, például szöveg beszúrásához, formázás megváltoztatásához, szakaszok hozzáadásához és még sok máshoz.

## Word dokumentum betöltése

Az első lépés az ODT-re konvertálni kívánt Word-dokumentum betöltése. A Dokumentum osztály segítségével töltse be a dokumentumot a forrásfájlból. Íme egy példa:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Ebben a példában a dokumentumok könyvtárában található "Document.docx" dokumentumot töltjük be.

## Biztonsági mentési beállítások konfigurálása

A következő lépés az ODT-re konvertálás biztonsági mentési beállításainak konfigurálása. Használja az OdtSaveOptions osztályt, és állítsa be a MeasureUnit tulajdonságot a kívánt értékre. Ha például hüvelyket szeretne használni mértékegységként, állítsa a MeasureUnit értéket OdtSaveMeasureUnit.Inches értékre. Íme, hogyan kell csinálni:

```csharp
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

Létrehozunk egy új OdtSaveOptions objektumot, és beállítjuk a MeasureUnit tulajdonságot a kívánt értékre, esetünkben az OdtSaveMeasureUnit.Inches-t, hogy a hüvelykeket használjuk mértékegységként.

## Konvertálja a dokumentumot ODT-re

Most, hogy konfiguráltuk a mentési beállításokat, folytathatjuk a dokumentum konvertálását ODT-re. A Dokumentum osztály Mentés metódusával mentheti a konvertált dokumentumot ODT formátumban a mentési beállítások megadásával. Íme egy példa:

```csharp
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Ebben a példában a konvertált dokumentumot "WorkingWithOdtSaveOptions.MeasureUnit.odt" néven mentjük a megadott mentési beállítások használatával.

### Példa forráskód az OdtSaveOptions "Mértékegység" funkcióval az Aspose.Words for .NET használatával



```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a Word dokumentumot
Document doc = new Document(dataDir + "Document.docx");

// Biztonsági opciók konfigurálása a "Mértékegység" funkcióval
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };

// Alakítsa át a dokumentumot ODT-re
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Következtetés

Ebben az útmutatóban elmagyaráztuk, hogyan konvertálhat Word-dokumentumot ODT-vé a mértékegység megadásával az OdtSaveOptions mentési beállításaival a .NET Aspose.Words könyvtárával. A megadott lépések követésével és a mellékelt C# forráskód használatával könnyedén alkalmazhatja ezt a funkciót a C# alkalmazásban. A mértékegység megadása az ODT-re konvertáláskor lehetővé teszi az eredményül kapott dokumentum formázásának és méreteinek szabályozását sajátos igényei szerint.