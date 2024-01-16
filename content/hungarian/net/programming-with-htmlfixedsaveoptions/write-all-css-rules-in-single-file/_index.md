---
title: Írja be az összes CSS-szabályt egyetlen fájlba
linktitle: Írja be az összes CSS-szabályt egyetlen fájlba
second_title: Aspose.Words Document Processing API
description: Tanulja meg, hogyan alakíthat át Word-dokumentumot rögzített HTML-vé az összes CSS-szabály egyetlen fájlba írásával az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-htmlfixedsaveoptions/write-all-css-rules-in-single-file/
---

Amikor egy Word-dokumentumot rögzített HTML-re konvertál egy C#-alkalmazásban, érdemes az összes CSS-szabályt egyetlen fájlba egyesíteni a jobb rendszerezés és hordozhatóság érdekében. A .NET Aspose.Words könyvtárával egyszerűen megadhatja ezt a funkciót a HtmlFixedSaveOptions mentési beállításaival. Ebben a részletes útmutatóban végigvezetjük, hogyan használhatja az Aspose.Words for .NET C# forráskódját Word-dokumentum rögzített HTML-formátumba való konvertálására úgy, hogy az összes CSS-szabályt egyetlen fájlba írja a HtmlFixedSaveOptions mentési beállításokkal.

## Az Aspose.Words könyvtár megértése

Mielőtt belemerülne a kódba, fontos megérteni a .NET Aspose.Words könyvtárát. Az Aspose.Words egy hatékony könyvtár Word dokumentumok létrehozásához, szerkesztéséhez, konvertálásához és védelméhez különböző platformokon, beleértve a .NET-et is. Számos funkciót kínál a dokumentumok kezeléséhez, például szöveg beszúrásához, formázás megváltoztatásához, szakaszok hozzáadásához és még sok máshoz.

## Word dokumentum betöltése

Az első lépés az, hogy betöltse a Word-dokumentumot, amelyet fix HTML-re szeretne konvertálni. A Dokumentum osztály segítségével töltse be a dokumentumot a forrásfájlból. Íme egy példa:

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

Ebben a példában a dokumentumok könyvtárában található "Document.docx" dokumentumot töltjük be.

## Biztonsági mentési beállítások konfigurálása

A következő lépés a mentési beállítások konfigurálása a rögzített HTML-re való konvertáláshoz. Használja a HtmlFixedSaveOptions osztályt, és állítsa a SaveFontFaceCssSeparately tulajdonságot false értékre, ha az összes CSS-szabályt egyetlen fájlba szeretné írni. Íme, hogyan kell csinálni:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };
```

Létrehozunk egy új HtmlFixedSaveOptions objektumot, és a SaveFontFaceCssSeparately tulajdonságot false értékre állítjuk, hogy az összes CSS-szabályt egyetlen fájlba írhassuk.

## Javított HTML dokumentum konvertálás

Most, hogy konfiguráltuk a mentési beállításokat, folytathatjuk a dokumentum konvertálását rögzített HTML-re. A Dokumentum osztály Mentés metódusával mentheti a konvertált dokumentumot rögzített HTML formátumba a mentési beállítások megadásával. Íme egy példa:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

Ebben a példában a konvertált dokumentumot "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html" néven mentjük a megadott mentési beállítások használatával.

### Példa a HtmlFixedSaveOptions forráskódjához az "Összes CSS-szabály írása egy fájlba" funkcióval az Aspose.Words for .NET használatával

```csharp
// Hozzáférési útvonal a dokumentumkönyvtárhoz
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a Word dokumentumot
Document doc = new Document(dataDir + "Document.docx");

// Konfigurálja a biztonsági mentési beállításokat az „Összes CSS-szabály írása egy fájlba” funkcióval
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { SaveFontFaceCssSeparately = false };

// Konvertálja a dokumentumot rögzített HTML formátumba
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.WriteAllCssRulesInSingleFile.html", saveOptions);
```

## Következtetés

Ebben az útmutatóban bemutattuk, hogyan alakíthat át Word-dokumentumot rögzített HTML-vé úgy, hogy az összes CSS-szabályt egyetlen fájlba írja a HtmlFixedSaveOptions és Aspose.Words könyvtár .NET-hez használatával. A megadott lépések követésével és a mellékelt C# forráskód használatával könnyedén alkalmazhatja ezt a funkciót a C# alkalmazásban. Az összes CSS-szabály egyetlen fájlba írása megkönnyíti a dokumentumkonverzió során generált HTML-kód rendszerezését és kezelését.