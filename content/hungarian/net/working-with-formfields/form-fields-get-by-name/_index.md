---
title: Űrlapmezők név szerint
linktitle: Űrlapmezők név szerint
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan kérheti le és módosíthatja név szerint az űrlapmezőket Word dokumentumokban az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/working-with-formfields/form-fields-get-by-name/
---

Ebben a lépésenkénti oktatóanyagban bemutatjuk, hogyan használhatja az Aspose.Words for .NET alkalmazást az űrlapmezők név szerinti lekéréséhez egy Word-dokumentumból. Elmagyarázzuk a mellékelt C# forráskódot, és megmutatjuk, hogyan implementálhatja azt saját projektjeibe.

 A kezdéshez győződjön meg arról, hogy az Aspose.Words for .NET telepítve van és be van állítva a fejlesztői környezetben. Ha még nem tette meg, töltse le és telepítse a könyvtárat innen[Aspose.Releases]https://releases.aspose.com/words/net/.

## 1. lépés: A dokumentumobjektum inicializálása

 Először inicializálja a`Document` objektumot az űrlapmezőket tartalmazó forrásdokumentum elérési útjának megadásával:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## 2. lépés: Űrlapmezők lekérése

 Ezután nyissa meg a`FormFields` tulajdona a`Range` objektum a dokumentumban az összes űrlapmező lekéréséhez:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Az űrlapmezőket index vagy név szerint is lekérheti. Ebben a példában mindkét módszerrel lekérünk egy űrlapmezőt:

```csharp
FormField formField1 = documentFormFields[3]; // Index alapján lekérés
FormField formField2 = documentFormFields["Text2"]; // Név szerinti visszakeresés
```

## 3. lépés: Az űrlapmező tulajdonságainak módosítása

Miután lekérte az űrlapmezőket, szükség szerint módosíthatja a tulajdonságaikat. Ebben a példában megváltoztatjuk a betűméretet`formField1` 20-ra és a betűszínre`formField2` pirosra:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## 4. lépés: A dokumentum mentése

Végül mentse el a módosított dokumentumot:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Ez az! Sikeresen lekérte az űrlapmezőket név szerint, és módosította tulajdonságaikat egy Word-dokumentumban az Aspose.Words for .NET használatával.

### Példa a Form Fields Get By Name forráskódjához az Aspose.Words for .NET használatával

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Nyugodtan használja ezt a kódot saját projektjeiben, és módosítsa saját igényei szerint.

### GYIK

#### K: Hogyan kaphatok név szerint űrlapmezőt az Aspose.Words-ben?

 V: Ha név szerint szeretne űrlapmezőt kapni az Aspose.Words programban, használja a`Document.Range.FormFields[name]` módszer. Ez a metódus a megadott névnek megfelelő űrlapmezőt adja vissza.

#### K: Mi a teendő, ha a megadott nevű űrlapmező nem létezik a dokumentumban?

 V: Ha a megadott nevű űrlapmező nem létezik a dokumentumban, a`Document.Range.FormFields[name]` módszer visszatér`null`. Ezt az eredményt bejelölheti az olyan esetek kezeléséhez, amikor az űrlapmező nem található.

#### K: Hogyan módosíthatom egy talált űrlapmező tulajdonságait?

V: Miután név szerint megkapja az űrlapmezőt, hozzáférhet annak egyedi tulajdonságaihoz, és szerkesztheti azokat. Például módosíthatja a mező értékét, engedélyezheti vagy letilthatja a láthatóságát, vagy szükség szerint módosíthat más tulajdonságokat.

#### K: Kaphatok több űrlapmezőt azonos néven egy dokumentumban?

 V: Igen, egy dokumentumban több, azonos nevű űrlapmező is szerepelhet. Ebben az esetben a`Document.Range.FormFields[name]` metódus az első talált űrlapmezőt adja vissza a megadott névvel. Ha több, azonos nevű űrlapmezővel rendelkezik, ezt figyelembe kell vennie a mezők kezelésekor.

#### K: Hogyan iterálhatom a dokumentum összes űrlapmezőjét?

 V: Ha egy dokumentumban az összes űrlapmezőt meg szeretné ismételni, használhatja a`foreach` hurok a`Document.Range.FormFields` Gyűjtemény. Ez lehetővé teszi, hogy minden űrlapmezőt külön-külön érjen el, és mindegyiken műveleteket hajtson végre.