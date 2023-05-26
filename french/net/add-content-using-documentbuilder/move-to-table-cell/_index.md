---
title: Déplacer vers la cellule du tableau
linktitle: Déplacer vers la cellule du tableau
second_title: Référence de l'API Aspose.Words pour .NET
description: Guide étape par étape pour utiliser Move To Table Cell dans Aspose.Words pour .NET
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/move-to-table-cell/
---

Dans cet exemple, nous vous expliquerons comment utiliser la fonction Move To Table Cell de Aspose.Words pour .NET en utilisant étape par étape le code source C# fourni. Cette fonctionnalité vous permet de naviguer et de manipuler des cellules spécifiques à l'intérieur d'un tableau dans un document Word. Suivez les étapes ci-dessous pour intégrer cette fonctionnalité dans votre application.

## Étape 1 : Chargez le document contenant le tableau

Tout d'abord, nous devons charger le document contenant le tableau dans lequel nous voulons déplacer la cellule. Utilisez le code suivant pour accomplir cette étape :

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Ce code charge le document spécifié (remplacez "MyDir + "Tables.docx"" avec le chemin réel de votre document contenant le tableau).

## Étape 2 : Déplacez le DocumentBuilder vers une cellule de tableau spécifique

Ensuite, nous allons déplacer le DocumentBuilder vers une cellule de tableau spécifique. Utilisez le code suivant pour effectuer cette étape :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

 Ce code crée un DocumentBuilder à partir du document existant, puis déplace le curseur du DocumentBuilder vers la cellule de tableau spécifiée. Enfin, il ajoute du contenu à cette cellule en utilisant le DocumentBuilder's`Write()` méthode.

## Étape 3 : Vérifier le résultat

Vous pouvez maintenant vérifier que le déplacement vers la cellule du tableau a réussi. Utilisez le code suivant pour accomplir cette étape :

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Ce code vérifie que la cellule spécifiée est bien la cellule actuelle du DocumentBuilder. Il vérifie également que le contenu ajouté par le DocumentBuilder a été correctement enregistré dans la cellule du tableau.

C'est tout ! Vous avez maintenant compris comment utiliser la fonctionnalité de déplacement vers une cellule de tableau d'Aspose.Words pour .NET à l'aide du code source fourni. Vous pouvez maintenant intégrer cette fonctionnalité dans votre propre application et manipuler des cellules de tableau spécifiques dans des documents Word.


### Exemple de code source pour passer à une cellule de tableau à l'aide de Aspose.Words pour .NET


```csharp

	Document doc = new Document(MyDir + "Tables.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Déplacez le générateur vers la ligne 3, cellule 4 du premier tableau.
	builder.MoveToCell(0, 2, 3, 0);
	builder.Write("\nCell contents added by DocumentBuilder");
	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
	Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());

```
