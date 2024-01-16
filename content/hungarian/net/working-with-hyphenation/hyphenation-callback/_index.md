---
title: Elválasztás visszahívás
linktitle: Elválasztás visszahívás
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan használhatja az Aspose.Words for .NET elválasztási visszahívását a szóelválasztás kezelésére.
type: docs
weight: 10
url: /hu/net/working-with-hyphenation/hyphenation-callback/
---

Ebben a lépésenkénti oktatóanyagban bemutatjuk, hogyan használhatja az Aspose.Words for .NET elválasztási visszahívási funkcióját. Elmagyarázzuk a mellékelt C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe.

 A kezdéshez győződjön meg arról, hogy az Aspose.Words for .NET telepítve van és konfigurálva van a fejlesztői környezetben. Ha még nem tette meg, töltse le és telepítse a könyvtárat innen[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. lépés: Mentse el az elválasztási emlékeztetőt

 Először is regisztráljuk az elválasztási visszahívást egyéni használatával`CustomHyphenationCallback` osztály. Ez lehetővé teszi számunkra, hogy a szavak elválasztását saját szabályaink szerint kezeljük:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

 Győződjön meg arról, hogy végrehajtotta a`CustomHyphenationCallback` osztály az Ön egyedi igényei szerint.

## 2. lépés: A dokumentum betöltése és elválasztás alkalmazása

Ezután töltse be a dokumentumot a megadott könyvtárból, és kötőjelezze el a szavakat az Aspose.Words használatával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## 3. lépés: A hiányzó szótárhibák kezelése

Ha hiányzik egy elválasztási szótár, elkapjuk a megfelelő kivételt, és hibaüzenetet jelenítünk meg:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## 4. lépés: Tisztítsa meg és tiltsa le az elválasztási emlékeztetőt

Végül a tisztaság és az elválasztási emlékeztető kikapcsolása érdekében hajtsa végre a következő lépéseket:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

Ez megtisztítja és letiltja az elválasztási emlékeztetőt a feldolgozás befejezése után.

Így ! Sikeresen használta az elválasztási visszahívást az Aspose.Words for .NET-ben.

### Forráskód minta elválasztási visszahíváshoz Aspose.Words .NET-hez

```csharp
try
{
	 // Regisztráljon elválasztási visszahívást.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Nyugodtan használhatja ezt a kódot saját projektjeiben, és módosíthatja sajátos igényei szerint.

### GYIK

#### K: Mit jelent az Aspose.Words szótagosítási emlékeztetője?

V: Az Aspose.Words szótagosítási emlékeztetője egy olyan funkció, amely lehetővé teszi a szavak szótagozásának testreszabását a dokumentumokban. A szótagosítási emlékeztető használatával egyéni szabályokat adhat meg a szavak szótagosításához, amelyek hasznosak lehetnek bizonyos nyelveknél vagy olyan helyzetekben, ahol az alapértelmezett szótagosítás nem hozza meg a kívánt eredményt.

#### K: Hogyan állíthat be szótagosítási emlékeztetőt az Aspose.Words-ben?

 V: Elválasztási visszahívás meghatározásához az Aspose.Wordsben létre kell hoznia egy osztályt, amely megvalósítja a`HyphenationCallback` interfész és valósítsa meg a`HandleWord()` módszer. Ezt a metódust minden egyes szótag esetében meg kell hívni. Egyéni szótagképzési szabályokat alkalmazhat rá, és visszaadhatja a szótagozott szót. Ezután kötheti az elválasztási visszahívást a`Document.HyphenationCallback` dokumentumának tulajdonsága.

#### K: Mi az előnye az Aspose.Words szótagosítási emlékeztetőjének?

V: Az Aspose.Words szótagosítási emlékeztetőjének használatának előnye, hogy testreszabhatja a szavak szótagolását a dokumentumokban. Ez nagyobb szabályozást biztosít a szótagosítás felett, különösen bizonyos nyelvek vagy forgatókönyvek esetén, ahol az alapértelmezett szótagosítás nem hozza meg a kívánt eredményt. Minden egyes szóra sajátos szabályokat alkalmazhat, hogy az igényeinek megfelelő pontos szótagozást kapjon.

#### K: Milyen gyakori forgatókönyvek fordulhatnak elő, amikor a szótagosítási emlékeztető hasznos lehet?

V: A szótagolás-erősítő használata számos forgatókönyv esetén hasznos lehet, például:
- Szavak szótagosítása meghatározott nyelveken, amelyeknek sajátos szótagolási szabályai vannak.
- A betűszavakra vagy szakszavakra személyre szabott szótagképzési szabályok alkalmazása.
- A szótagolás stiláris preferenciáinak vagy tipográfiai szabványoknak megfelelő adaptálása.

#### K: Hogyan tesztelhetem az egyéni szótagozást az Aspose.Words szótagosítási emlékeztetőjével?

 V: Ha az Aspose.Words szótagosítási emlékeztetővel szeretné tesztelni az egyéni szótagozást, létrehozhat egy tesztdokumentumot, amely olyan szavakat tartalmaz, amelyekre egyéni szótagképzési szabályokat kíván alkalmazni. Ezután beállíthatja az egyéni szótagozás visszahívását, hívja a`Document.Range.Replace()` módszerrel helyettesítheti a szavakat a dokumentumban, és használja a`Hyphenate()` módszere a`Hyphenation` osztályban, hogy megkapjuk a szavak szótagolását. Ezután szükség szerint formázhatja a szótagozott szavakat, például kötőjelek hozzáadásával a szótagok közé.