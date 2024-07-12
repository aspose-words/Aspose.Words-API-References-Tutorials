---
title: Mértékegységek közötti konvertálás
linktitle: Mértékegységek közötti konvertálás
second_title: Aspose.Words Document Processing API
description: Útmutató lépésről lépésre a mértékegységek közötti konvertáláshoz egy dokumentumban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/programming-with-document-properties/convert-between-measurement-units/
---

Ebben az oktatóanyagban végigvezetjük a C# forráskódon a mértékegységek közötti konvertáláshoz az Aspose.Words for .NET segítségével. Ez a funkció lehetővé teszi a margók, fejléc- és lábléctávolságok stb. megadását különböző mértékegységekben.

## 1. lépés: A projekt beállítása

A kezdéshez hozzon létre egy új C#-projektet kedvenc IDE-jében. Győződjön meg arról, hogy az Aspose.Words for .NET könyvtárra hivatkozik a projektben.

## 2. lépés: A dokumentum és a konstruktor létrehozása

Ebben a lépésben létrehozunk egy új dokumentumot, és inicializáljuk a konstruktort. Használja a következő kódot:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 3. lépés: A mértékegységek konfigurálása

Most átváltjuk a margók, fejléc- és lábléctávolságok stb. értékeit különböző mértékegységekre. A következő kóddal adja meg az értékeket meghatározott mértékegységekben:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Ez a kód a`ConvertUtil` osztályú Aspose.Words a megadott értékek hüvelykké konvertálásához (`InchToPoint`). Használhat más konverziós módszereket is, amelyek elérhetők a`ConvertUtil` osztály az értékek más mértékegységekre való konvertálásához.

### Példa forráskód a Mértékegységek közötti konvertáláshoz az Aspose.Words for .NET használatával

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Most megtanulta, hogyan konvertálhat a mértékegységek között margók, fejléc- és lábléctávolságok stb. megadásakor egy dokumentumban az Aspose.Words for .NET használatával. Az ebben az oktatóanyagban található lépésenkénti útmutatót követve könnyedén megadhatja a kívánt mértékegységekben megadott értékeket saját dokumentumaiban.