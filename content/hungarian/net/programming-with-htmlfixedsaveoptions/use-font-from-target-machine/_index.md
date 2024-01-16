---
title: Használja a célgépről származó betűtípust
linktitle: Használja a célgépről származó betűtípust
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan alakíthat át Word-dokumentumot rögzített HTML-formátumba a célgép betűtípusaival az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-htmlfixedsaveoptions/use-font-from-target-machine/
---

Amikor egy Word-dokumentumot rögzített HTML-re konvertál egy C#-alkalmazásban, érdemes a célgép betűtípusait használni annak biztosítására, hogy a renderelt HTML megőrizze a dokumentum eredeti megjelenését és stílusát. A .NET Aspose.Words könyvtárával egyszerűen megadhatja ezt a funkciót a HtmlFixedSaveOptions mentési beállításaival. Ebben a részletes útmutatóban végigvezetjük, hogyan használhatja az Aspose.Words for .NET C#-forráskódját Word-dokumentumok fix HTML-formátumba konvertálásához a célgép betűtípusaival a HtmlFixedSaveOptions használatával.

## Az Aspose.Words könyvtár megértése

Mielőtt belemerülne a kódba, fontos megérteni a .NET Aspose.Words könyvtárát. Az Aspose.Words egy hatékony könyvtár Word dokumentumok létrehozásához, szerkesztéséhez, konvertálásához és védelméhez különböző platformokon, beleértve a .NET-et is. Számos funkciót kínál a dokumentumok kezeléséhez, például szöveg beszúrásához, formázás megváltoztatásához, szakaszok hozzáadásához és még sok máshoz.

## Word dokumentum betöltése

Az első lépés az, hogy betöltse a Word-dokumentumot, amelyet fix HTML-re szeretne konvertálni. A Dokumentum osztály segítségével töltse be a dokumentumot a forrásfájlból. Íme egy példa:

```csharp
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");
```

Ebben a példában betöltjük a dokumentumok könyvtárában található "Felsoroláspontok alternatív fonttal.docx" dokumentumot.

## Biztonsági mentési beállítások konfigurálása

következő lépés a mentési beállítások konfigurálása a rögzített HTML-re való konvertáláshoz. Használja a HtmlFixedSaveOptions osztályt, és állítsa a UseTargetMachineFonts tulajdonságot true értékre, hogy az Aspose.Words a célgépről származó betűtípusokat használja. Íme, hogyan kell csinálni:

```csharp
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };
```

Létrehozunk egy új HtmlFixedSaveOptions objektumot, és igazra állítjuk a UseTargetMachineFonts tulajdonságot, hogy a célgép betűtípusait használjuk a konvertálás során.

## Javított HTML dokumentum konvertálás

Most, hogy konfiguráltuk a mentési beállításokat, folytathatjuk a dokumentum konvertálását rögzített HTML-re. A Dokumentum osztály Mentés metódusával mentheti a konvertált dokumentumot rögzített HTML formátumba a mentési beállítások megadásával. Íme egy példa:

```csharp
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

Ebben a példában a konvertált dokumentumot "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html" néven mentjük a megadott mentési beállítások használatával.

### Példa a HtmlFixedSaveOptions forráskódjához a „Célgép betűtípusainak használata” funkcióval az Aspose.Words for .NET használatával

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a Word dokumentumot
Document doc = new Document(dataDir + "Bullet points with alternative font.docx");

//Konfigurálja a biztonsági mentési beállításokat a „Betűtípusok használata a célgépről” funkcióval
HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { UseTargetMachineFonts = true };

// Konvertálja a dokumentumot rögzített HTML formátumba
doc.Save(dataDir + "WorkingWithHtmlFixedSaveOptions.UseFontFromTargetMachine.html", saveOptions);
```

## Következtetés

Ebben az útmutatóban elmagyaráztuk, hogyan alakíthat át Word-dokumentumot rögzített HTML-formátumba a célgép betűtípusaival az Aspose.Words könyvtár .NET-hez segítségével. A megadott lépések követésével és a mellékelt C# forráskód használatával könnyedén alkalmazhatja ezt a funkciót a C# alkalmazásban. A rögzített HTML-re konvertálás a célgép betűtípusaival garantálja a dokumentum hű és következetes megjelenítését HTML formátumban.
