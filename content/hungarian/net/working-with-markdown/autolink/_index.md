---
title: Autolink
linktitle: Autolink
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan szúrhat be automatikus linket az Aspose.Words for .NET segítségével Lépésről lépésre.
type: docs
weight: 10
url: /hu/net/working-with-markdown/autolink/
---

Ebben a példában elmagyarázzuk, hogyan kell használni az "Autolink" funkciót az Aspose.Words for .NET-hez. Ez a funkció lehetővé teszi a hiperhivatkozások automatikus beszúrását a dokumentumba.

## 1. lépés: Dokumentumgenerátor használata

Először egy dokumentumgenerátort fogunk használni, hogy tartalmat adjunk a dokumentumunkhoz.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## 2. lépés: Hiperhivatkozás beszúrása

 A hiperhivatkozást a`InsertHyperlink` a dokumentumgenerátor módszere. Megadjuk az URL-t és a hivatkozáshoz megjelenítendő szöveget.

```csharp
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
```

## 3. lépés: E-mail cím beszúrása hivatkozásként

E-mail címet is beszúrhatunk hivatkozásként a "mailto:" előtag használatával. Ez lehetővé teszi a felhasználók számára, hogy a hivatkozásra kattintva megnyitják alapértelmezett levelezőprogramjukat.

```csharp
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```

## 4. lépés: A dokumentum mentése

Végül elmenthetjük a dokumentumot a kívánt formátumban.

### Példa forráskódra az Aspose.Words for .NET használatával történő automatikus linkhez


```csharp
// Használjon dokumentumkészítőt, hogy tartalmat adjon a dokumentumhoz.
DocumentBuilder builder = new DocumentBuilder();

// Hiperhivatkozás beszúrása.
builder.InsertHyperlink("https://www.aspose.com", "https://www.aspose.com", false);
builder.InsertHyperlink("email@aspose.com", "mailto:email@aspose.com", false);
```


Gratulálok ! Megtanulta az "Autolink" funkció használatát az Aspose.Words for .NET-hez.


### GYIK

#### K: Hogyan hozhatok létre automatikus hivatkozást egy URL-címre az Aspose.Words-ben?

 V: Az Aspose.Words URL-címére mutató automatikus hivatkozás létrehozásához használhatja a`<a>` címkével a`href` URL-címet tartalmazó attribútum. Például használhatja`<a href="https://www.aspose.com">https://www.aspose.com</a>` hogy automatikusan hivatkozzon a „https://www.aspose.com” oldalra.

#### K: Testreszabható egy automatikus hivatkozás megjelenített szövege az Aspose.Words-ben?

 V: Igen, személyre szabhatja az Aspose.Words automatikus hivatkozásának megjelenített szövegét. Ahelyett, hogy az URL-címet használná megjelenített szövegként, bármilyen más szöveget is használhat, ha lecseréli a tartalmat a között`<a>` címkéket. Például használhatja`<a href="https://www.aspose.com">Click here</a>` a "Kattintson ide" szöveg automatikus hivatkozásként való megjelenítéséhez.

#### K: Hogyan adhatok hozzá további attribútumokat az Aspose.Words automatikus linkjéhez?

V: Ha további attribútumokat szeretne hozzáadni az Aspose.Words automatikus hivatkozásaihoz, további HTML-attribútumokat használhat a`<a>` címke. Például használhatja`<a href="https://www.aspose.com" target="_blank">Link</a>` a hivatkozás új ablakban vagy lapon való megnyitásához a` attribute target="_blank"`.