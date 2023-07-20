---
title: Créer un tableau dans un document Word
linktitle: Créer un tableau dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Apprenez à créer un tableau dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/build-table/
---
Dans ce didacticiel pas à pas, vous apprendrez à créer un tableau dans un document Word à l'aide de Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de créer un tableau avec une mise en forme et un contenu personnalisés à l'aide de la classe DocumentBuilder.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : créer un nouveau document
Pour commencer, créez un nouveau document en utilisant la classe Document :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : Démarrer le tableau
Ensuite, utilisez la méthode StartTable de la classe DocumentBuilder pour commencer à construire la table :

```csharp
Table table = builder.StartTable();
```

## Étape 3 : Insérer des cellules et ajouter du contenu
Désormais, vous pouvez insérer des cellules dans le tableau et leur ajouter du contenu à l'aide des méthodes InsertCell et Write de la classe DocumentBuilder. Personnalisez la mise en forme des cellules selon vos besoins :

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Étape 4 : terminer la rangée
Après avoir ajouté du contenu aux cellules de la première ligne, utilisez la méthode EndRow de la classe DocumentBuilder pour terminer la ligne :

```csharp
builder.EndRow();
```

## Étape 5 : Personnalisez le formatage des lignes
Vous pouvez personnaliser la mise en forme d'une ligne en définissant les propriétés des objets RowFormat et CellFormat :

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Étape 6 : terminer la table
Pour compléter le tableau, utilisez la méthode EndTable de la classe DocumentBuilder :

```csharp
builder.EndTable();
```

### Exemple de code source pour la construction d'une table à l'aide de Aspose.Words pour .NET
Voici le code source complet pour construire une table en utilisant Aspose.Words pour .NET :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Conclusion
Toutes nos félicitations! Vous avez appris avec succès à créer un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais créer des tableaux avec une mise en forme personnalisée.

### FAQ pour la table de construction dans un document Word

#### Q : Qu'est-ce qu'Aspose.Words pour .NET ?

R : Aspose.Words pour .NET est une puissante bibliothèque de traitement de documents qui permet aux développeurs de créer, lire, modifier et convertir des documents Microsoft Word par programme dans des applications .NET. Il fournit un large éventail de fonctionnalités pour travailler avec des documents Word, telles que la manipulation de texte, la création de tableaux, la protection de documents, le formatage, etc.

#### Q : Comment créer un tableau dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour créer un tableau dans un document Word à l'aide d'Aspose.Words pour .NET, vous pouvez suivre ces étapes :
1.  Créez une nouvelle instance de`Document` classe et une`DocumentBuilder` objet.
2.  Utilisez le`StartTable` méthode de la`DocumentBuilder` classe pour commencer à construire le tableau.
3. Insérez des cellules dans le tableau et ajoutez du contenu à l'aide de la`InsertCell` et`Write` méthodes de la`DocumentBuilder` classe.
4.  Terminez le rang à l'aide de la`EndRow` méthode de la`DocumentBuilder` classe.
5.  Personnalisez la mise en forme des lignes en définissant les propriétés du`RowFormat` et`CellFormat` objets.
6.  Terminez le tableau à l'aide de`EndTable` méthode de la`DocumentBuilder` classe.
7. Enregistrez le document.

#### Q : Comment puis-je personnaliser la mise en forme du tableau et de ses cellules ?

 R : Vous pouvez personnaliser la mise en forme du tableau et de ses cellules en définissant diverses propriétés du`RowFormat` et`CellFormat` objets. Par exemple, vous pouvez ajuster l'alignement des cellules, l'orientation verticale et horizontale du texte, la hauteur des cellules, la hauteur des lignes, etc. En utilisant ces propriétés, vous pouvez obtenir l'apparence souhaitée pour le tableau et son contenu.

#### Q : Puis-je créer des tableaux complexes avec des cellules fusionnées et d'autres fonctionnalités avancées ?

 R : Oui, Aspose.Words pour .NET fournit des fonctionnalités avancées pour créer des tableaux complexes, y compris la prise en charge des cellules fusionnées, des tableaux imbriqués et des mises en page de tableaux complexes. Vous pouvez utiliser le`MergeCells` méthode pour fusionner des cellules,`StartTable`méthode pour créer des tables imbriquées et d'autres méthodes pour obtenir la structure de table souhaitée.

#### Q : Aspose.Words pour .NET est-il compatible avec différents formats de document Word ?

R : Oui, Aspose.Words pour .NET est compatible avec divers formats de documents Word, notamment DOC, DOCX, RTF, etc. Il prend en charge les formats hérités (DOC) et les formats XML modernes (DOCX) et vous permet de travailler avec des documents dans différents formats sans aucun problème.

#### Q : Où puis-je trouver plus d'informations et de documentation sur Aspose.Words pour .NET ?

 R : Vous pouvez trouver une documentation complète et des exemples de code sur[Références API](https://reference.aspose.com/words/net/). La documentation fournira des informations détaillées sur les fonctionnalités de la bibliothèque et comment les utiliser dans vos applications .NET.