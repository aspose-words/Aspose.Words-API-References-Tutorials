---
title: Olvassa el az Active XControl tulajdonságait a Word fájlból
linktitle: Olvassa el az Active XControl tulajdonságait a Word fájlból
second_title: Aspose.Words Document Processing API
description: Olvassa be az ActiveX-vezérlők tulajdonságait egy Word-fájlban az Aspose.Words for .NET segítségével.
type: docs
weight: 10
url: /hu/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---

Ebben a lépésenkénti útmutatóban bemutatjuk, hogyan olvashatja be az ActiveX-vezérlők tulajdonságait egy Word-fájlban az Aspose.Words for .NET használatával. Megadjuk Önnek a teljes forráskódot, és megmutatjuk, hogyan kell formázni a markdown kimenetet.

## 1. lépés: A dokumentum inicializálása

 Az első lépés a`Document` objektumot az ActiveX-vezérlőket tartalmazó Word-dokumentum betöltésével. Feltétlenül cserélje ki`MyDir` a dokumentumot tartalmazó könyvtár tényleges elérési útjával.

```csharp
Document doc = new Document(MyDir + "ActiveX controls.docx");
```

## 2. lépés: Az ActiveX-vezérlők helyreállítása

 Ebben a lépésben mindegyiket megismételjük`Shape` dokumentumból az ActiveX-vezérlők lekéréséhez és tulajdonságaik beolvasásához.

```csharp
string properties = "";
foreach(Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
     if (shape.OleFormat is null) break;

     OleControl oleControl = shape.OleFormat.OleControl;
     if (oleControl.IsForms2OleControl)
     {
         Forms2OleControl checkBox = (Forms2OleControl)oleControl;
         properties = properties + "\nCaption: " + checkBox.Caption;
         properties = properties + "\nValue: " + checkBox.Value;
         properties = properties + "\nEnabled: " + checkBox.Enabled;
         properties = properties + "\nType: " + checkBox.Type;
         if (checkBox. ChildNodes != null)
         {
             properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
         }

         properties += "\n";
     }
}

properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
Console.WriteLine("\n" + properties);
```

### Példa forráskódra az Active XControl Properties olvasásához az Aspose.Words for .NET használatával

Itt található a teljes forráskód az ActiveX-vezérlők tulajdonságainak olvasásához az Aspose.Words for .NET használatával:

```csharp
	Document doc = new Document(MyDir + "ActiveX controls.docx");

	string properties = "";
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
	{
		if (shape.OleFormat is null) break;

		OleControl oleControl = shape.OleFormat.OleControl;
		if (oleControl.IsForms2OleControl)
		{
			Forms2OleControl checkBox = (Forms2OleControl) oleControl;
			properties = properties + "\nCaption: " + checkBox.Caption;
			properties = properties + "\nValue: " + checkBox.Value;
			properties = properties + "\nEnabled: " + checkBox.Enabled;
			properties = properties + "\nType: " + checkBox.Type;
			if (checkBox.ChildNodes != null)
			{
				properties = properties + "\nChildNodes: " + checkBox.ChildNodes;
			}

			properties += "\n";
		}
	}

	properties = properties + "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
	Console.WriteLine("\n" + properties);
```

## Következtetés

Ez az útmutató bemutatja, hogyan olvashatja be az ActiveX-vezérlők tulajdonságait Word-fájlban az Aspose.Words for .NET használatával. A leírt lépések követésével inicializálhatja a dokumentumot, lekérheti az ActiveX-vezérlőket, és beolvashatja azok tulajdonságait. Használja kiindulópontként a megadott mintakódot, és szabja testre egyedi igényei szerint.

Az ActiveX-vezérlők tulajdonságainak beolvasása lehetővé teszi, hogy fontos információkat nyerjen ki az ezeket a vezérlőket tartalmazó Word-fájlokból. Az Aspose.Words for .NET hatékony szolgáltatásokat kínál az ActiveX-vezérlőkkel rendelkező szövegfeldolgozáshoz és a dokumentumfeldolgozás automatizálásához.

### GYIK

#### K: Mi az első lépés az ActiveX-vezérlők tulajdonságainak beolvasásához egy Word-fájlban?

 V: Az első lépés a`Document` objektumot az ActiveX-vezérlőket tartalmazó Word-dokumentum betöltésével. Feltétlenül cserélje ki`MyDir` a dokumentumot tartalmazó könyvtár tényleges elérési útjával.

#### K: Hogyan tölthetek be ActiveX-vezérlőket a dokumentumba?

 V: Az ActiveX-vezérlők lekéréséhez mindegyiket ismételnie kell`Shape` dokumentumot, és ellenőrizze, hogy az ActiveX-vezérlő-e. Használja a`OleFormat` tulajdona`Shape` hozzáférni a`OleControl` objektumot és lekérni a szükséges tulajdonságokat.

#### K: Az ActiveX-vezérlők milyen tulajdonságait olvashatom?

V: Elolvashatja az ActiveX-vezérlők különféle tulajdonságait, például a feliratot, az értéket, az engedélyezett vagy letiltott állapotot, a típust és a vezérlőhöz társított gyermekcsomópontokat.

#### K: Hogyan tudhatom meg a dokumentumban található ActiveX-vezérlők teljes számát?

 V: A dokumentumban található ActiveX-vezérlők teljes számának megtekintéséhez használja a`GetChildNodes` módszere a`Document` objektum, amely megadja a`NodeType.Shape` típusát és a gyermek csomópontokat is beleértve.