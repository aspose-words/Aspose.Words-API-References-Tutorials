---
title: Tartalomra mutató hivatkozás konfigurálása
linktitle: Tartalomra mutató hivatkozás konfigurálása
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a dokumentum tartalmára való hivatkozás beállításához az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-properties/configuring-link-to-content/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon, hogy beállíthassa a tartalomhoz való hivatkozást az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi, hogy egy dokumentum adott tartalmára hivatkozzon.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum és a konstruktor létrehozása

Ebben a lépésben létrehozunk egy új dokumentumot, és inicializáljuk a konstruktort. Használja a következő kódot:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: Hozzon létre egy könyvjelzőt

Most létrehozunk egy könyvjelzőt a dokumentumban. A következő kóddal hozzon létre egy könyvjelzőt szöveggel:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Ez a kód létrehoz egy "MyBookmark" nevű könyvjelzőt, és szöveget ad hozzá.

## 4. lépés: A tartalomhivatkozás beállítása

Most a dokumentum tulajdonságaival konfiguráljuk a tartalomra mutató hivatkozást. Használja a következő kódot a tartalomra mutató hivatkozás hozzáadásához és lekéréséhez:

```csharp
// Szerezze meg a dokumentum összes egyéni tulajdonságának listáját.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Tartalomhoz kötött tulajdonság hozzáadása.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Ez a kód hozzáad egy "Könyvjelző" nevű tartalomhoz kapcsolódó tulajdonságot a "Saját könyvjelzőm" könyvjelzővel. Ezután lekéri a tartalommal kapcsolatos tulajdonságinformációkat, például a hivatkozás állapotát, a hivatkozás forrását és a tulajdonság értékét.

### Példa forráskódra a tartalomhoz való hivatkozás konfigurálásához az Aspose.Words for .NET használatával

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Az összes egyéni dokumentumtulajdonság listájának lekérése a fájlból.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Hivatkozás hozzáadása a tartalomtulajdonhoz.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Most megtanulta, hogyan konfigurálhatja a tartalomra mutató hivatkozást egy dokumentumban az Aspose.Words for .NET használatával. Az ebben az oktatóanyagban található, lépésenkénti útmutatót követve egyszerűen hozhat létre és konfigurálhat hivatkozásokat saját dokumentumaiban meghatározott tartalmakra.