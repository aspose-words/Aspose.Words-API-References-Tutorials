---
title: Déplacer vers la cellule du tableau dans un document Word
linktitle: Déplacer vers la cellule du tableau dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour utiliser Déplacer vers la cellule du tableau dans la fonctionnalité de document Word d'Aspose.Words pour .NET
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/move-to-table-cell/
---
Dans cet exemple, nous vous expliquerons comment utiliser la fonctionnalité Déplacer vers une cellule de tableau dans un document Word d'Aspose.Words pour .NET en utilisant étape par étape le code source C# fourni. Cette fonctionnalité vous permet de naviguer et de manipuler des cellules spécifiques dans un tableau d'un document Word. Suivez les étapes ci-dessous pour intégrer cette fonctionnalité dans votre application.

## Étape 1 : Charger le document contenant le tableau

Tout d’abord, nous devons charger le document contenant le tableau dans lequel nous voulons déplacer la cellule. Utilisez le code suivant pour accomplir cette étape :

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Ce code charge le document spécifié (remplacez "MyDir + "Tables.docx"" avec le chemin réel de votre document contenant le tableau).

## Étape 2 : déplacer le DocumentBuilder vers une cellule de tableau spécifique

Ensuite, nous allons déplacer DocumentBuilder vers une cellule de tableau spécifique. Utilisez le code suivant pour effectuer cette étape :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

Ce code crée un DocumentBuilder à partir du document existant, puis déplace le curseur du DocumentBuilder vers la cellule de tableau spécifiée. Enfin, il ajoute du contenu à cette cellule à l'aide de l'outil DocumentBuilder.`Write()` méthode.

## Étape 3 : Vérifiez le résultat

Vous pouvez maintenant vérifier que le déplacement vers la cellule du tableau a réussi. Utilisez le code suivant pour accomplir cette étape :

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Ce code vérifie que la cellule spécifiée est bien la cellule actuelle du DocumentBuilder. Il vérifie également que le contenu ajouté par DocumentBuilder a été correctement enregistré dans la cellule du tableau.

C'est tout ! Vous avez maintenant compris comment utiliser la fonctionnalité de déplacement vers une cellule de tableau d'Aspose.Words pour .NET à l'aide du code source fourni. Vous pouvez désormais intégrer cette fonctionnalité dans votre propre application et manipuler des cellules de tableau spécifiques dans des documents Word.


### Exemple de code source pour passer à une cellule de tableau à l'aide d'Aspose.Words for .NET


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

## Conclusion

Dans cet exemple, nous avons exploré la fonctionnalité Déplacer vers une cellule de table d’Aspose.Words pour .NET. Nous avons appris comment charger un document contenant un tableau, déplacer DocumentBuilder vers une cellule de tableau spécifique et ajouter du contenu à cette cellule. Cette fonctionnalité fournit aux développeurs des outils puissants pour parcourir et manipuler des cellules spécifiques dans les tableaux de documents Word par programmation à l'aide d'Aspose.Words pour .NET. Il peut constituer un ajout précieux à votre application pour le traitement dynamique de documents Word et la gestion du contenu des tableaux.

### FAQ pour le déplacement vers une cellule de tableau dans un document Word

#### Q : Quel est l'objectif de la fonctionnalité Déplacer vers une cellule de tableau dans Aspose.Words pour .NET ?

R : La fonctionnalité Déplacer vers une cellule de tableau dans Aspose.Words pour .NET permet aux développeurs de naviguer et de manipuler des cellules spécifiques à l'intérieur d'un tableau dans un document Word par programme. Il offre la possibilité d'insérer, de modifier ou de supprimer du contenu dans une cellule particulière.

#### Q : Comment déplacer DocumentBuilder vers une cellule de tableau spécifique dans un document Word ?

: Pour déplacer DocumentBuilder vers une cellule de tableau spécifique dans un document Word, vous pouvez utiliser la méthode MoveToCell de la classe DocumentBuilder. Cette méthode prend les indices de la ligne et de la cellule cibles dans le tableau comme paramètres et place le curseur au début de cette cellule.

#### Q : Puis-je ajouter ou modifier du contenu après avoir été déplacé vers une cellule de tableau spécifique à l'aide de la fonctionnalité Déplacer vers une cellule de tableau ?

R : Oui, une fois que DocumentBuilder est positionné sur la cellule du tableau souhaitée à l'aide de MoveToCell, vous pouvez utiliser diverses méthodes de la classe DocumentBuilder, telles que Write, Writeln ou InsertHtml, pour ajouter ou modifier le contenu de cette cellule.

#### Q : Comment puis-je vérifier que le déplacement vers la cellule du tableau a réussi ?

R : Vous pouvez vérifier le déplacement réussi vers la cellule du tableau en vérifiant la position du curseur de DocumentBuilder. Par exemple, vous pouvez comparer le nœud actuel de DocumentBuilder avec la cellule vers laquelle vous aviez l'intention de vous déplacer et vérifier que le contenu ajouté par DocumentBuilder est correctement enregistré dans la cellule du tableau.