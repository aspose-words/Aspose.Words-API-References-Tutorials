---
title: Mezőkód
linktitle: Mezőkód
second_title: Aspose.Words Document Processing API
description: Lépésről lépésre útmutató mezőkód és mezőeredmény beszerzéséhez a Word-dokumentumokban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-fields/field-code/
---

Itt található egy lépésről lépésre bemutatott útmutató a C# forráskód leírásához, amely az Aspose.Words for .NET "Mezőkód lekérése" funkcióját használja. A kívánt eredmény elérése érdekében gondosan kövesse az egyes lépéseket.

## 1. lépés: Dokumentumkönyvtár beállítása

A megadott kódban meg kell adnia dokumentumai könyvtárát. Cserélje le a „DOKUMENTUMKÖNYVTÁR” értéket a dokumentumkönyvtár megfelelő elérési útjára.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: A dokumentum betöltése

Első lépésként töltse fel azt a dokumentumot, ahová a mezőkódokat szeretné beszerezni.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

Feltétlenül cserélje ki a „Hyperlinks.docx” fájlt a saját fájl nevére.

## 3. lépés: Tallózás a dokumentummezők között

 Használjuk a`foreach` hurok a dokumentumban található összes mező áthaladásához.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 A ciklus minden iterációján megkapjuk a mezőkódot a`GetFieldCode()` módszer. A mező eredményét is egy változóban tároljuk.

### Forráskód-példa az Aspose.Words mezőkód lekéréséhez .NET-hez

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Lapozás a dokumentummezők között.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // Tegyen valamit a mező kódjával és eredményével.
}
```

Ebben a példában betöltöttünk egy dokumentumot, majd végigjártuk a dokumentumban található összes mezőt. Minden iterációnál megkaptuk a kódot és a mező eredményét. Felveheti saját logikáját a kód és az eredménymezők szükség szerinti feldolgozásához.

Ezzel véget is értünk az Aspose.Words for .NET "Mezőkód lekérése" funkciójának használatáról szóló útmutatónknak.

### GYIK

#### K: Hogyan illeszthetek be mezőt egy Word dokumentumba az Aspose.Words for .NET használatával?

 V: Ha egy mezőt Word-dokumentumba szeretne beszúrni az Aspose.Words for .NET használatával, használja a`DocumentBuilder.InsertField` módszer, amely megadja a megfelelő mezőkódot. Például használhatja`builder.InsertField("MERGEFIELD CustomerName")` összevonási mező beszúrásához a dokumentumba.

#### K: Hogyan frissíthetem a dokumentum mezőit az Aspose.Words for .NET használatával?

 V: A dokumentummezők Aspose.Words for .NET használatával frissítéséhez használhatja a`Document.UpdateFields`módszer. Ez frissíti a dokumentumban lévő összes mezőt, például az egyesített mezőket, a dátummezőket stb.

#### K: Hogyan kérhetem le egy adott mező értékét az Aspose.Words for .NET-ben?

 V: Egy adott mező értékének lekéréséhez az Aspose.Words for .NET-ben, használja a`Field.GetResult` módszert a mező indexének megadásával a`Document.Range.Fields` Gyűjtemény. Például használhatja`string value = document.Range.Fields[0].GetResult()` hogy lekérje a dokumentum első mezőjének értékét.

#### K: Hogyan távolíthatok el egy mezőt a dokumentumból az Aspose.Words for .NET használatával?

 V: Ha egy mezőt szeretne eltávolítani egy dokumentumból az Aspose.Words for .NET használatával, használja a`Field.Remove` módszer, amely meghatározza a`Field` az eltávolítani kívánt objektumot. Ezzel eltávolítja a mezőt a dokumentumból.