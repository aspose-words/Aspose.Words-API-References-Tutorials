---
title: Sorolja fel a Használati célstílusokat
linktitle: Sorolja fel a Használati célstílusokat
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan kapcsolhat össze és fűzhet hozzá Word-dokumentumokat, miközben megőrzi a céldokumentum listastílusait az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/join-and-append-documents/list-use-destination-styles/
---

Ez az oktatóanyag végigvezeti Önt az Aspose.Words for .NET List Use Destination Styles funkciójának használatán. Ez a funkció lehetővé teszi Word-dokumentumok összekapcsolását és hozzáfűzését a céldokumentum listastílusainak használata közben.

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

Ezután be kell töltenie a forrás- és céldokumentumot az Aspose.Words használatával`Document` osztály. Frissítse a fájlneveket a`Document` konstruktor a dokumentumnevek szerint.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## 3. lépés: Állítsa a Forrásdokumentumot Folytatásra a céldokumentum után

 Annak biztosításához, hogy a forrásdokumentum tartalma a céldokumentum vége után is folytatódjon, be kell állítania a`SectionStart` a forrásdokumentum első szakaszának tulajdonsága`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## 4. lépés: Kezelje a lista formázását

A lista formázásának kezeléséhez ismételje meg a forrásdokumentum minden bekezdését, és ellenőrizze, hogy listaelem-e. Ha igen, akkor összehasonlítja a listaazonosítót a céldokumentumban lévő meglévő listákkal. Ha létezik azonos azonosítójú lista, akkor létrehoz egy másolatot a listáról a forrásdokumentumban, és frissíti a bekezdés listaformátumát a másolt lista használatához.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## 5. lépés: Csatolja a forrásdokumentumot a céldokumentumhoz

 Most hozzáfűzheti a forrásdokumentumot a céldokumentumhoz a segítségével`AppendDocument` módszere a`Document` osztály. A`ImportFormatMode.UseDestinationStyles` paraméter biztosítja, hogy a céldokumentum listastílusait használjuk a hozzáfűzési művelet során.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## 6. lépés: Mentse el a záródokumentumot

Végül mentse az egyesített dokumentumot a Célstílusok listázása funkcióval, amely engedélyezve van a segítségével`Save` módszere a`Document` osztály.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Példa forráskód a List Use Destination Styles használatához Aspose.Words for .NET használatával 

Íme a teljes forráskód a "Cél-stílusok listája" funkciójához C# nyelven az Aspose.Words for .NET használatával:


```csharp
	// A dokumentumkönyvtár elérési útja
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Állítsa be a forrásdokumentumot úgy, hogy közvetlenül a céldokumentum vége után folytassa.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Kövesse nyomon a létrehozott listákat.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Ellenőrizze, hogy a céldokumentum tartalmaz-e már listát ezzel az azonosítóval. Ha igen, akkor lehet
			// hogy a két lista együtt futjon. Inkább készítsen másolatot a listáról a forrásdokumentumban.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Ehhez az azonosítóhoz már létezik újonnan másolt lista, kérje le a tárolt listát,
				// és használja az aktuális bekezdésben.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Adja hozzá a lista másolatát a dokumentumhoz, és tárolja későbbi hivatkozás céljából.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Állítsa be ennek a bekezdésnek a listáját a másolt listára.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Csatolja a forrásdokumentumot a céldokumentum végéhez.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Ez az! Sikeresen megvalósította a List Use Destination Styles szolgáltatást az Aspose.Words for .NET használatával. A végső dokumentum az egyesített tartalmat fogja tartalmazni a céldokumentum listastílusaival.