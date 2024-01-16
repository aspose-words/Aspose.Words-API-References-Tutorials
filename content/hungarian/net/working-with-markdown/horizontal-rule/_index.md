---
title: Vízszintes szabály
linktitle: Vízszintes szabály
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan illeszthet be vízszintes szabályt az Aspose.Words for .NET segítségével Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/horizontal-rule/
---

Ebben a példában bemutatjuk, hogyan használhatja a vízszintes szabály funkciót az Aspose.Words for .NET-hez. A vízszintes szabály a dokumentum szakaszainak vizuális elkülönítésére szolgál.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. lépés: Vízszintes szabály beszúrása

 Beszúrhatunk egy vízszintes szabályt a`InsertHorizontalRule` a dokumentumgenerátor módszere.

```csharp
builder. InsertHorizontalRule();
```

## Minta forráskód a vízszintes szabályhoz az Aspose.Words for .NET segítségével

```csharp
// Használjon dokumentumkészítőt, hogy tartalmat adjon a dokumentumhoz.
DocumentBuilder builder = new DocumentBuilder();

// Szúrjon be vízszintes szabályt.
builder.InsertHorizontalRule();
```

Gratulálok ! Most megtanulta a vízszintes szabály funkció használatát az Aspose.Words for .NET-ben.


### GYIK

#### K: Hogyan hozhatok létre vízszintes vonalzót a Markdown alkalmazásban?

V: Vízszintes vonalzó létrehozásához a Markdown alkalmazásban használhatja a következő szimbólumok egyikét egy üres sorban: három csillag (\***), három kötőjel (\---), vagy három aláhúzás (\___).

#### K: Testreszabhatom a vízszintes vonalzó megjelenését a Markdown alkalmazásban?

V: A szabványos Markdownban nincs mód a vízszintes vonalzók megjelenésének testreszabására. Néhány fejlett Markdown szerkesztő és bővítmény azonban további testreszabási funkciókat kínál.

#### K: Minden Markdown szerkesztő támogatja a vízszintes vonalzókat?

V: Igen, a legnépszerűbb Markdown szerkesztők támogatják a vízszintes vonalzókat. Azonban mindig a legjobb, ha megnézi az adott szállító dokumentációját, hogy megbizonyosodjon arról, hogy az támogatott.

#### K: Milyen egyéb elemeket hozhatok létre a Markdownban?

V: A vízszintes vonalzókon kívül a Markdownban címeket, bekezdéseket, listákat, hivatkozásokat, képeket, táblázatokat és egyebeket is létrehozhat.