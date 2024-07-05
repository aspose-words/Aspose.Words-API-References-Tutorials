---
title: Használjon szóközt szintenként a lista behúzásához
linktitle: Használjon szóközt szintenként a lista behúzásához
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a szóköz használatához szintenként a lista behúzásához az Aspose.Words for .NET-ben. Könnyedén hozhat létre jól strukturált Word dokumentumokat.
type: docs
weight: 10
url: /hu/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Az Aspose.Words for .NET egy hatékony könyvtár Word dokumentumok létrehozásához, szerkesztéséhez és kezeléséhez C# alkalmazásokban. Az Aspose.Words szolgáltatásai között szerepel az a lehetőség, hogy szintenként egy szóköz karaktert használjon a listák behúzásához. Ebben az útmutatóban bemutatjuk, hogyan használhatja az Aspose.Words for .NET C# forráskódját a funkció megvalósításához.

## Az Aspose.Words könyvtár megértése

Mielőtt belemerülne a kódba, fontos megérteni a .NET Aspose.Words könyvtárát. Az Aspose.Words egy népszerű könyvtár, amely egyszerűvé és hatékonysá teszi a Word-dokumentumokkal végzett szövegfeldolgozást. Funkciók széles skáláját kínálja a Word dokumentumok létrehozásához, módosításához és kezeléséhez, beleértve a listák kezelését és a behúzást.

## A dokumentum létrehozása és tartalom hozzáadása

Az első lépés egy új dokumentum létrehozása és tartalom hozzáadása. Új dokumentumpéldány létrehozásához használja a Dokumentum osztályt. Ezután a DocumentBuilder osztály segítségével szöveget adjon hozzá, és hozzon létre egy listát többszintű behúzással. Íme egy példa:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Hozzon létre egy listát három behúzási szinttel
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

Ebben a példában új dokumentumot hozunk létre, és a DocumentBuilder segítségével szöveget adunk hozzá, és létrehozunk egy listát három behúzási szinttel. Három elemet adtunk hozzá a listához, mindegyik elem behúzásával egy további szinttel.

## Egy szóköz használata szintenként a lista behúzásához

A tartalom hozzáadása után a listák behúzását szintenként egy szóköz karakterrel konfigurálhatjuk. Ehhez a TxtSaveOptions osztályt használjuk, és a ListIndentation.Count tulajdonságot a behúzási szintek számára, a ListIndentation.Character tulajdonságot pedig a használandó szóköz karakterre állítjuk. Itt van, hogyan:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

Ebben a példában létrehozzuk a TxtSaveOptions egy példányát, és a ListIndentation.Count tulajdonságot 3-ra állítjuk, jelezve, hogy a listában három behúzási szint található. A ListIndentation.Character tulajdonságot a behúzáshoz használni kívánt szóköz karakterre (' ') is beállítjuk.

### Példa forráskódra az Aspose.Words for .NET "Egy szóköz karakter használata szintenként a lista behúzásához" funkcióhoz

Íme az Aspose.Words for .NET "Szintenként egy szóköz használata a lista behúzásához" funkció teljes mintaforráskódja:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // A dokumentumkönyvtár elérési útja
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Hozzon létre egy dokumentumot, és adjon hozzá tartalmat
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Hozzon létre egy listát három behúzási szinttel
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Használjon szintenként egy szóköz karaktert a lista behúzásához
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // Mentse el a dokumentumot a megadott opciókkal
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## Következtetés

Ebben az útmutatóban elmagyaráztuk, hogyan használható az Aspose.Words for .NET a "Szintenként egy szóköz karakter használata a lista behúzásához" funkció alkalmazására. A megadott lépések követésével és a mellékelt C# forráskód használatával könnyedén konfigurálhatja a listák behúzását a Word-dokumentumokban, szintenként egy szóköz karakterrel. Az Aspose.Words óriási rugalmasságot és teljesítményt kínál a szövegfeldolgozáshoz szövegformázással és listakezeléssel, lehetővé téve, hogy jól strukturált dokumentumokat hozzon létre a C# alkalmazásban.

### Gyakran Ismételt Kérdések

#### K: Mi az Aspose.Words for .NET?
Az Aspose.Words for .NET egy hatékony könyvtár Word dokumentumok létrehozásához, szerkesztéséhez és kezeléséhez C# alkalmazásokban. Számos funkciót kínál a Word-dokumentumokkal végzett szövegfeldolgozáshoz, beleértve azt is, hogy szintenként egy szóközt használhat a listák behúzásához.

#### K: Hogyan használhatok szintenként egy szóközt a lista behúzására az Aspose.Words for .NET segítségével?
Az alábbi lépések végrehajtásával szintenként egy szóközt használhat a lista behúzásához:

 Hozzon létre egy új dokumentumot a`Document` osztály.

 Használja a`DocumentBuilder`osztályt, hogy tartalmat adjon a dokumentumhoz, és hozzon létre egy listát többszintű behúzással.

 Miután hozzáadta a tartalmat és konfigurálta a lista behúzását, használja a`TxtSaveOptions` osztályt, és állítsa be a`ListIndentation.Count` tulajdonság a behúzási szintek számához és a`ListIndentation.Character` ingatlan a téren (`' '`) használni.

 Mentse el a dokumentumot a megadott opciókkal a`Save` módszere a`Document` osztály.

#### K: Az Aspose.Words támogat más karaktereket a lista behúzásához?
Igen, az Aspose.Words más karaktereket is támogat a behúzó listáknál. Használhat nem szóköz karaktereket, például tabulátorokat (`'\t'` ) vagy más speciális karaktereket a`ListIndentation.Character` tulajdonság a kívánt karakterhez.

#### K: Testreszabható a szóközök száma szintenként a lista behúzásához?
 Igen, testreszabhatja a szóközök számát szintenként a lista behúzásához az érték módosításával`ListIndentation.Count` ingatlan a`TxtSaveOptions` osztály. Minden behúzási szinthez megadhatja a szóközök számát.

#### K: Milyen egyéb funkciókat kínál az Aspose.Words a listakezeléshez?
Az Aspose.Words számos szolgáltatást kínál a Word dokumentumok listáinak kezelésére. Létrehozhat számozott vagy felsorolásjeles listákat, behúzási szinteket állíthat be, testreszabhatja a listák stílusát, hozzáadhat listaelemeket stb.