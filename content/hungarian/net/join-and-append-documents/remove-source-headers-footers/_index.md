---
title: Távolítsa el a forrásfejlécek láblécét
linktitle: Távolítsa el a forrásfejlécek láblécét
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan távolíthat el fejlécet és láblécet Word-dokumentumok egyesítése és hozzáfűzése közben az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/remove-source-headers-footers/
---

Ez az oktatóanyag végigvezeti az Aspose.Words for .NET forrásfejléc-láblécek eltávolítása funkciójának használatán. Ez a funkció lehetővé teszi Word-dokumentumok összekapcsolását és hozzáfűzését, miközben eltávolítja a fejléceket és lábléceket a forrásdokumentumból.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

1. Az Aspose.Words for .NET telepítve van. Letöltheti az Aspose webhelyéről, vagy telepítheti a NuGet segítségével.
2. Visual Studio vagy bármely más C# fejlesztői környezet.

## 1. lépés: Inicializálja a dokumentumkönyvtárakat

 Először is be kell állítania a dokumentumkönyvtár elérési útját. Módosítsa az értékét`dataDir` változó ahhoz az elérési úthoz, ahol a dokumentumok találhatók.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 2. lépés: Töltse be a forrás- és céldokumentumot

Ezután be kell töltenie a forrás- és céldokumentumot az Aspose.Words használatával.`Document` osztály. Frissítse a fájlneveket a`Document` konstruktor a dokumentumnevek szerint.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## 3. lépés: Távolítsa el a fejléceket és lábléceket a forrásdokumentum szakaszaiból

 Ha el szeretné távolítani a fejléceket és a lábléceket a forrásdokumentum egyes szakaszaiból, ismételje meg a szakaszokat a a használatával`foreach` hurok, és hívja a`ClearHeadersFooters` módszer.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## 4. lépés: Tiltsa le a „LinkToPrevious” beállítást a HeadersFooters számára

Még a fejlécek és láblécek forrásdokumentumból való törlése után is fennáll annak a lehetősége, hogy a „LinkToPrevious” beállítás`HeadersFooters` még beállítható. Ennek a viselkedésnek a elkerülése érdekében kifejezetten be kell állítania`false` az első szakaszhoz`HeadersFooters` ingatlan.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## 5. lépés: Csatolja a forrásdokumentumot a céldokumentumhoz

 Most hozzáfűzheti a forrásdokumentumot a céldokumentumhoz a segítségével`AppendDocument` módszere a`Document` osztály. A`ImportFormatMode.KeepSourceFormatting` paraméter biztosítja, hogy a forrás formázása megmaradjon a hozzáfűzési művelet során.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## 6. lépés: Mentse el a záródokumentumot

 Végül mentse az egyesített dokumentumot a Forrásfejléc-láblécek eltávolítása funkcióval a`Save` módszere a`Document` osztály.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Példa forráskód a Forrásfejlécek lábléceinek eltávolításához az Aspose.Words for .NET használatával 

Íme a teljes forráskód a „Forrásfejléc-láblécek eltávolítása” funkcióhoz C# nyelven az Aspose.Words for .NET használatával:


```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Távolítsa el a fejléceket és lábléceket a forrásdokumentum egyes szakaszaiból.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Még a fejlécek és láblécek forrásdokumentumból való törlése után is a „LinkToPrevious” beállítás
	// a HeadersFooters továbbra is beállítható. Ez azt eredményezi, hogy a fejlécek és láblécek a célállomástól folytatódnak
	// dokumentum. Ennek a viselkedésnek a elkerülése érdekében ezt hamis értékre kell állítani.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Ez az! Sikeresen implementálta a Forrásfejléc-láblécek eltávolítása funkciót az Aspose.Words for .NET használatával. A végső dokumentum az egyesített tartalmat tartalmazza majd a forrásdokumentumból eltávolított fejlécekkel és láblécekkel.