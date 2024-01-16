---
title: Előnyben részesített vezérlőtípus Word dokumentumban
linktitle: Előnyben részesített vezérlőtípus Word dokumentumban
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre az előnyben részesített vezérlőtípus megadásához a Word-dokumentumban HTML-dokumentum Aspose.Words for .NET segítségével történő betöltésekor.
type: docs
weight: 10
url: /hu/net/programming-with-htmlloadoptions/preferred-control-type/
---
Ez a cikk lépésenkénti útmutatót tartalmaz az előnyben részesített vezérlőtípus használatához az Aspose.Words for .NET-hez. Részletesen elmagyarázzuk a kód minden részét. Ennek az oktatóanyagnak a végén megértheti, hogyan kell megadni az előnyben részesített vezérlőtípust HTML-dokumentum betöltésekor.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette és konfigurálta az Aspose.Words for .NET könyvtárat a projektben. A könyvtárat és a telepítési utasításokat az Aspose webhelyén találja.

## 1. lépés: Határozza meg a HTML kódot

 A kezdéshez meg kell határoznia a dokumentumként betölteni kívánt HTML-kódot. Ebben a példában definiáltunk egy`html` változó, amely egy választó HTML kódját tartalmazza opciókkal.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## 2. lépés: Állítsa be a HTML-betöltési beállításokat

 Ezután létrehozunk egy`HtmlLoadOptions` objektumot és állítsa be a`PreferredControlType`tulajdonát`HtmlControlType.StructuredDocumentTag`. Ez arra utasítja az Aspose.Words-t, hogy a StructuredDocumentTag-eket használja a HTML megjelenítésére betöltéskor.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## 3. lépés: Töltse be és mentse a dokumentumot

 Használjuk a`Document` osztályt a HTML-kód memóriafolyamból való betöltéséhez a korábban meghatározott betöltési beállításokkal. Ezután a megadott könyvtárba mentjük a dokumentumot a`.docx`fájlformátum.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Példa forráskódra a preferált vezérlőtípushoz az Aspose.Words for .NET-hez

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Ez minden ! Sikeresen megadta az előnyben részesített vezérlőtípust egy HTML-dokumentum Aspose.Words for .NET segítségével történő betöltésekor.

## Következtetés

 Ennek a lépésenkénti útmutatónak a követésével megtanulta, hogyan használhatja az Aspose.Words for .NET "Preferred Control Type" funkcióját a kívánt vezérlőtípus megadására HTML-dokumentum betöltésekor. Beállítása a`PreferredControlType`tulajdonát`HtmlControlType.StructuredDocumentTag` lehetővé teszi az Aspose.Words számára a StructuredDocumentTags (SDT) használatát a HTML-tartalom jobb megjelenítése és feldolgozása érdekében. Más vezérlési típusokat is felfedezhet sajátos igényeinek megfelelően. Ennek a funkciónak a használata biztosítja a HTML-dokumentumok pontos és hatékony kezelését a C#-alkalmazásban az Aspose.Words segítségével.

### GYIK az előnyben részesített vezérlőtípusokhoz a Word dokumentumban

#### K: Mi az Aspose.Words for .NET "Preferred Control Type" szolgáltatása?

V: Az "Előnyben részesített vezérlőtípus" funkció lehetővé teszi, hogy megadja a HTML elemeket megjelenítő vezérlőelemek preferált típusát a HTML-dokumentum betöltésekor. Segít a megfelelő vezérlőtípus kiválasztásában a HTML-tartalom jobb megjelenítéséhez és feldolgozásához.

#### K: Hogyan állíthatom be az előnyben részesített vezérlőtípust HTML-dokumentum betöltésekor?

 V: Az előnyben részesített vezérlőtípus beállításához létre kell hoznia egy`HtmlLoadOptions` objektumot, és állítsa be`PreferredControlType` ingatlan a kívántnak`HtmlControlType` . A megadott példában`HtmlControlType.StructuredDocumentTag` használt.

#### K: Mi a jelentősége a StructuredDocumentTags (SDT) preferált vezérlőtípusként való használatának?

V: A StructuredDocumentTags (SDT) XML-alapú elemek, amelyek segítségével összetett tartalmat és vezérlőket jeleníthet meg egy Word-dokumentumban. Az SDT-k preferált vezérlőtípusként történő használata jobb kompatibilitást és a HTML-tartalom megjelenítését biztosíthatja.

#### K: Hogyan biztosíthatom, hogy az Aspose.Words az előnyben részesített vezérlőtípust használja a HTML-dokumentum betöltésekor?

 V: Beállítva a`PreferredControlType`tulajdonát`HtmlControlType.StructuredDocumentTag`amint az a példa forráskódjában látható, az Aspose.Words SDT-ket használ a HTML elemek megjelenítésére a dokumentum betöltésekor.

#### K: Használhatok más vezérlőtípusokat preferált lehetőségként?

 V: Igen, azon kívül`HtmlControlType.StructuredDocumentTag` , Az Aspose.Words for .NET más vezérlőtípusokat is támogat, mint pl`HtmlControlType.ContentControl` és`HtmlControlType.CustomXmlMarkup`.