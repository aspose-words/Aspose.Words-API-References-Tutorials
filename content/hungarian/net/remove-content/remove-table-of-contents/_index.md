---
title: Távolítsa el a tartalomjegyzéket a Word-dokumentumból
linktitle: Távolítsa el a tartalomjegyzéket a Word-dokumentumból
second_title: Aspose.Words Document Processing API
description: Ismerje meg, hogyan távolíthatja el a tartalomjegyzéket egy Word-dokumentumból az Aspose.Words for .NET használatával.
type: docs
weight: 10
url: /hu/net/remove-content/remove-table-of-contents/
---
Ebben az oktatóanyagban végigvezetjük, hogyan távolíthatja el a tartalomjegyzéket egy Word-dokumentumból a .NET Aspose.Words könyvtárával. A tartalomjegyzék néha redundáns vagy szükségtelen lehet, és ez a kód segít hatékonyan eltávolítani. Lépésről lépésre nyújtunk útmutatót, amely segít megérteni és megvalósítani a kódot saját .NET-projektjében.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
- C# programozási nyelv gyakorlati ismerete
- A projektben telepített .NET Aspose.Words könyvtár
- A törölni kívánt tartalomjegyzéket tartalmazó Word-dokumentum

## 1. lépés: Határozza meg a dokumentumkönyvtárat
 Először is be kell állítania a könyvtár elérési útját a Word-dokumentum helyére. Cserélje ki`"YOUR DOCUMENT DIRECTORY"` a kódban a megfelelő elérési úttal.

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 2. lépés: Töltse fel a dokumentumot
 Ezután betöltjük a Word-dokumentumot a`Document` osztály segítségével a`Load` módszer.

```csharp
// Töltse be a dokumentumot
Document doc = new Document(dataDir + "your-document.docx");
```

## 3. lépés: Törölje a tartalomjegyzéket
 A tartalomjegyzék eltávolításához a TOC (tartalomjegyzék) típuson keresztül futunk`FieldStart` csomópontok a dokumentumban. Ezeket a csomópontokat tároljuk, hogy gyorsan elérhessük őket, és létrehozhassuk a törölni kívánt csomópontok listáját.

```csharp
// Tárolja a TOC mezők FieldStart csomópontjait a dokumentumban a gyors hozzáférés érdekében.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Ez egy lista a megadott tartalomjegyzékben található csomópontok tárolására. A módszer végén törlődnek.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
     if (start.FieldType == FieldType.FieldTOC)
     {
         fieldStarts.Add(start);
     }
}

// Ellenőrizze, hogy létezik-e a megadott TOC index.
if (index > fieldStarts.Count - 1)
     throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
     // Biztonságosabb ezeket a csomópontokat tárolni, és a végén törölni.
     nodeList.Add(currentNode);
     currentNode = currentNode.NextPreOrder(doc);

     // Amikor egy FieldTOC típusú FieldEnd csomóponttal találkozunk,
     //tudjuk, hogy a jelenlegi TOC végén vagyunk, és itt megállunk.
     if (currentNode.NodeType == NodeType.FieldEnd)
     {
         FieldEnd fieldEnd = (FieldEnd)currentNode;
         if (fieldEnd.FieldType == FieldType.FieldTOC)


             isRemoving = false;
     }
}

foreach(Node node in nodeList)
{
     node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```


### Minta forráskód a tartalomjegyzék eltávolításához az Aspose.Words for .NET használatával 
```csharp

// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// Töltse be a dokumentumot
Document doc = new Document(dataDir + "your-document.docx");

// Tárolja a TOC mezők FieldStart csomópontjait a dokumentumban a gyors hozzáférés érdekében.
List<FieldStart> fieldStarts = new List<FieldStart>();
// Ez egy lista a megadott tartalomjegyzékben található csomópontok tárolására. A módszer végén eltávolítják őket.
List<Node> nodeList = new List<Node>();

foreach (FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
	if (start.FieldType == FieldType.FieldTOC)
	{
		fieldStarts.Add(start);
	}
}

// Győződjön meg arról, hogy az átadott index által meghatározott tartalomjegyzék létezik.
if (index > fieldStarts.Count - 1)
	throw new ArgumentOutOfRangeException("TOC index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
	// Biztonságosabb ezeket a csomópontokat tárolni, és később egyszerre törölni.
	nodeList.Add(currentNode);
	currentNode = currentNode.NextPreOrder(doc);

	// Ha találkozunk egy FieldTOC típusú FieldEnd csomóponttal,
	// tudjuk, hogy a jelenlegi TOC végén vagyunk, és itt megállunk.
	if (currentNode.NodeType == NodeType.FieldEnd)
	{
		FieldEnd fieldEnd = (FieldEnd) currentNode;
		if (fieldEnd.FieldType == FieldType.FieldTOC)
			isRemoving = false;
	}
}

foreach (Node node in nodeList)
{
	node.Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
        
```

## Következtetés
Ebben az oktatóanyagban egy lépésről lépésre bemutatott útmutatót mutattunk be a tartalomjegyzék Word-dokumentumból való eltávolításához az Aspose.Words könyvtár .NET-hez segítségével. A mellékelt kód és utasítások követésével könnyedén eltávolíthatja a tartalomjegyzéket, és javíthatja a dokumentum elrendezését. Ne felejtse el igazítani a könyvtár elérési útját és a fájlneveket az Ön egyedi igényeihez.

### GYIK

#### K: Miért használjam az Aspose.Words programot a Word-dokumentum tartalomjegyzékének eltávolításához?

V: Az Aspose.Words egy hatékony és sokoldalú osztálykönyvtár Word-dokumentumok manipulálására .NET-alkalmazásokban. Az Aspose.Words használatával hatékonyan eltávolíthatja a tartalomjegyzéket a dokumentumokból, ami akkor lehet hasznos, ha a tartalomjegyzék redundáns vagy szükségtelen. Ez lehetővé teszi a dokumentum tartalmának testreszabását és általános megjelenítésének javítását.

#### K: Hogyan tölthetek fel egy dokumentumot az Aspose.Words for .NET-be?

V: A Word-dokumentum tartalomjegyzékének eltávolításához először be kell töltenie a dokumentumot a memóriába az Aspose.Words Load() metódusával. Íme egy mintakód egy dokumentum egy adott könyvtárból való betöltéséhez:

```csharp
// A dokumentumkönyvtár elérési útja
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Töltse be a dokumentumot
Document doc = new Document(dataDir + "your-document.docx");
```

 Cserélje ki`"YOUR DOCUMENTS DIRECTORY"` a dokumentum tényleges elérési útjával.

#### K: Hogyan távolíthatom el a tartalomjegyzéket egy dokumentumból az Aspose.Words használatával?

 V: A TOC eltávolításához ismételje meg a`FieldStart` írja be a TOC csomópontjait a dokumentumba. Ezeket a csomópontokat tárolhatja a gyors hozzáférés érdekében, és létrehozhatja a törölni kívánt csomópontok listáját. Itt van egy minta kód:

```csharp
// Tárolja a TOC mezők FieldStart csomópontjait a dokumentumban a gyors hozzáférés érdekében.
List<FieldStart> fieldStarts = new List<FieldStart>();
//Ez egy lista a megadott tartalomjegyzékben található csomópontok tárolására. A módszer végén törlődnek.
List<Node> nodeList = new List<Node>();

foreach(FieldStart start in doc.GetChildNodes(NodeType.FieldStart, true))
{
if (start.FieldType == FieldType.FieldTOC)
{
fieldStarts.Add(start);
}
}

// Ellenőrizze, hogy létezik-e a megadott tartalomjegyzék index.
if (index > fieldStarts.Count - 1)
throw new ArgumentOutOfRangeException("Table of contents index is out of range");

bool isRemoving = true;

Node currentNode = fieldStarts[index];
while (isRemoving)
{
// Biztonságosabb ezeket a csomópontokat tárolni, és a végén törölni.
nodeList.Add(currentNode);
currentNode = currentNode.NextPreOrder(doc);

// Amikor egy FieldTOC típusú FieldEnd csomóponttal találkozunk,
//tudjuk, hogy a jelenlegi TOC végén vagyunk, és itt megállunk.
if (currentNode.NodeType == NodeType.FieldEnd)
{
FieldEnd fieldEnd = (FieldEnd)currentNode;
if (fieldEnd.FieldType == FieldType.FieldTOC)
isRemoving = false;
}
}

foreach(Node node in nodeList)
{
node. Remove();
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

#### K: Hogyan lehet elmenteni a szerkesztett dokumentumot az Aspose.Words for .NET-be?

V: A tartalomjegyzék törlése után el kell mentenie a módosított dokumentumot a Save() metódussal. Adja meg a kívánt kimeneti fájl elérési útját és formátumát (pl. DOCX) a szerkesztett dokumentumhoz. Itt van egy minta kód:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```