---
title: Mezőfrissítési kultúraforrás módosítása
linktitle: Mezőfrissítési kultúraforrás módosítása
second_title: Aspose.Words Document Processing API
description: Mező-frissítési kultúraforrás módosítása, Lépésről lépésre útmutató a kultúraforrás módosításához az Aspose.Words for .NET-ben.
type: docs
weight: 10
url: /hu/net/working-with-fields/change-field-update-culture-source/
---

Ebben az oktatóanyagban végigvezetjük a Word-dokumentumok mezőfrissítési kultúraforrásának megváltoztatásán az Aspose.Words for .NET használatával. A kultúraforrás módosításával szabályozhatja a dátumformátumot a mezőfrissítési és körlevél-műveletek során. Ennek eléréséhez megadjuk a szükséges C# forráskódot és lépésről lépésre.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Az Aspose.Words for .NET könyvtár telepítve van a rendszerére.

## 1. lépés: Hozzon létre egy dokumentumot és a DocumentBuildert
Kezdésként hozzon létre egy példányt a Document osztályból és egy DocumentBuilder objektumból:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 2. lépés: Tartalom beszúrása adott területi beállítással
Ezután állítsa be a nyelvet németre, és szúrjon be dátumformátumú mezőket:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

A fenti kódban a betűtípus nyelvi beállítását németre (1031-es területi azonosító) állítjuk be, és két mezőt szúrunk be meghatározott dátumformátummal.

## 3. lépés: Mezőfrissítési kultúraforrás módosítása
A mezőfrissítési kultúraforrás módosításához használja a FieldOptions osztályt:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

Ebben a példában a mező frissítése során használt kultúrát úgy állítjuk be, hogy a mező által használt kultúra közül válasszuk ki.

## 4. lépés: Hajtsa végre a körlevélkészítést
Hajtson végre egy körlevél műveletet, és adja meg a dátum értékét a "Date2" mezőben:

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

Ebben a kódrészletben végrehajtjuk a körlevél-műveletet, és megadjuk a DateTime értéket a "Date2" mezőben.

## 5. lépés: Mentse el a dokumentumot
Mentse el a módosított dokumentumot fájlba a Dokumentum osztály Mentés metódusával:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Példa forráskód a mezőfrissítési kultúraforrás megváltoztatásához az Aspose.Words for .NET használatával
Íme a teljes forráskód a Word dokumentumok mezőfrissítési kultúraforrásának Aspose.Words for .NET használatával történő módosításához:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan módosíthatja a mező frissítési kultúra forrását a Word dokumentumokban az Aspose.Words for .NET használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód felhasználásával immár vezérelheti a dátumformázáshoz használt kultúrát a mezőfrissítési és körlevél-műveletek során. Szabja testre a kultúraforrást igényei szerint, hogy biztosítsa a pontos és következetes dátumot.

### GYIK

#### K: Hogyan módosíthatom a helyszíni frissítési kultúraforrást az Aspose.Words for .NET-ben?

 V: A mezőfrissítési kultúraforrás módosításához az Aspose.Words for .NET-ben, használja a`Document.FieldOptions.CultureSource` tulajdonságot, és állítsa be értékét`FieldCultureSource.FieldCode` vagy`FieldCultureSource.CurrentThread` . Például használhatja`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` mezőkódban meghatározott kultúra használatához.

#### K: Hogyan adhatok meg egy adott kultúrát az Aspose.Words for .NET mezőinek frissítéséhez?

 V: Ha egy adott kultúrát szeretne megadni az Aspose.Words for .NET mezőinek frissítéséhez, használja a`Document.FieldOptions.FieldUpdateCultureInfo` tulajdonság és állítsa be a`CultureInfo` a kívánt kultúrának megfelelő tárgy. Például használhatja`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` a francia (francia) kultúra pontosítására.

#### K: Letiltható az automatikus mezőfrissítés az Aspose.Words for .NET-ben?

 V: Igen, az Aspose.Words for .NET-ben letiltható az automatikus mezőfrissítés. Használhatja a`Document.FieldOptions.UpdateFields` tulajdonságot, és állítsa be`false` hogy megakadályozza a mezők automatikus frissítését. Ez lehetővé teszi a mezők szükség szerinti manuális frissítését.

#### K: Hogyan frissíthetem manuálisan a dokumentummezőket az Aspose.Words for .NET-ben?

 V: Egy dokumentum mezőinek manuális frissítéséhez az Aspose.Words for .NET programban használja a`Field.Update` módszer minden mezőre külön-külön. Például használhatja`field.Update()` az adott mező frissítéséhez.