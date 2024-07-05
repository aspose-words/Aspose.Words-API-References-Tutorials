---
title: Escape URI a PDF dokumentumban
linktitle: Escape URI a PDF dokumentumban
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre Hogyan távolítsuk el az URI-t PDF-dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-pdfsaveoptions/escape-uri/
---

Ez a cikk lépésről lépésre bemutatja az URI-t PDF-dokumentumban az Aspose.Words for .NET-hez való használatával. Részletesen elmagyarázzuk a kód minden részét. Ennek az oktatóanyagnak a végén megértheti, hogyan illeszthet be hiperhivatkozásokat egy dokumentumba a megtisztított Uri-val.

Mielőtt elkezdené, győződjön meg arról, hogy telepítette és konfigurálta az Aspose.Words for .NET könyvtárat a projektben. A könyvtárat és a telepítési utasításokat az Aspose webhelyén találja.

## 1. lépés: Határozza meg a dokumentumkönyvtárat

 A kezdéshez meg kell határoznia annak a könyvtárnak az elérési útját, ahol a dokumentumok találhatók. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Hozzon létre egy dokumentumot és egy DocumentBuilder programot

 Ezután létre kell hoznunk egy újat`Document` tárgy és a`DocumentBuilder` objektumot a dokumentum felépítéséhez.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Szúrjon be hiperhivatkozásokat megtisztított Uri-val

 Használja a`InsertHyperlink` módszere a`DocumentBuilder` objektumot a hiperhivatkozások dokumentumba való beillesztéséhez. Az Uri-t a következővel kell kiszabadítani`Uri.EscapeUriString` funkció a formázási hibák elkerülése érdekében.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), hamis);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), hamis);
```

## 4. lépés: Mentse el a dokumentumot PDF formátumban

 Végül a dokumentumot PDF formátumban menthetjük el a`Save` módszere a`Document` tárgy. Adja meg a kimeneti fájl nevét.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

Ez minden ! Az Aspose.Words for .NET segítségével sikeresen beszúrta a megtisztított Uri-t tartalmazó hiperhivatkozásokat egy dokumentumba.

### Az Aspose.Words for .NET-hez tartozó Uri forráskódja


```csharp

	// A dokumentumok könyvtárának elérési útja.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", false);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", false);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## Következtetés

Ebben az oktatóanyagban bemutattuk, hogyan lehet az Aspose.Words for .NET használatával megkerülni az URI-ket egy PDF-dokumentumban. Az URI-k kihagyásával elkerülheti a formázási hibákat, és biztosíthatja a hiperhivatkozások helyes értelmezését és megjelenítését a PDF-dokumentumban. Kövesse a leírt lépéseket a megtisztított URI-vel rendelkező hiperhivatkozások PDF-dokumentumába való beillesztéséhez. Mindenképpen menekülj.

### Gyakran Ismételt Kérdések

#### K: Mi az a escape URI egy PDF-dokumentumban, és miért fontos?
V: Az Escape URI egy PDF-dokumentumban arra a módszerre utal, amely az URL-ben található speciális karaktereket escape-szekvenciákká alakítja a formázási hibák elkerülése érdekében. Ez azért fontos, mert az URL-ben található speciális karakterek megzavarhatják az URL szerkezetét, és félreértelmezéshez vagy helytelen megjelenítéshez vezethetnek. A speciális karakterek kihagyásával garantáljuk, hogy az URL helyesen értelmeződik és megjelenik a PDF dokumentumban.

#### K: Hogyan használhatom az Aspose.Words for .NET-et az URI-k megkerülésére egy PDF-dokumentumban?
V: Az Aspose.Words for .NET használatával az URI-k kikerüléséhez PDF-dokumentumban, kövesse az alábbi lépéseket:

 Cseréléssel állítsa be a könyvtár elérési útját, ahol a dokumentumok találhatók`"YOUR DOCUMENT DIRECTORY"` a dokumentumkönyvtár tényleges elérési útjával.

 Hozzon létre egy új példányt a`Document` osztály és a`DocumentBuilder` objektumot a dokumentum felépítéséhez.

 Használja a`InsertHyperlink` módszere a`DocumentBuilder` objektumot a hiperhivatkozások dokumentumba való beillesztéséhez. Ügyeljen arra, hogy elkerülje az URI-t a`Uri.EscapeUriString` funkció a formázási hibák elkerülése érdekében.

 Használja a`Save` módszere a`Document` objektumot a dokumentum PDF formátumban történő mentéséhez a kimeneti fájl nevének megadásával.

#### K: Milyen előnyei vannak az URI-k kihagyásának egy PDF-dokumentumban?
V: A PDF-dokumentumban megjelenő URI előnyei a következők:

Formázási hibák megelőzése: Az URI-kihagyás segít megelőzni az URL-ben szereplő speciális karakterek által okozott formázási hibákat, biztosítva, hogy az URL megfelelően értelmezhető és megjelenjen a PDF-dokumentumban.

Kompatibilitás PDF-olvasókkal: A kikerült URI-ket általában jól támogatják a PDF-olvasók, így jobb kompatibilitást és egységes felhasználói élményt biztosítanak.

#### K: Milyen speciális karaktereket kell megtisztítani egy URI-ban?
 V: Az URI-ben meg kell szabadítani a következő speciális karaktereket: szóköz, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.