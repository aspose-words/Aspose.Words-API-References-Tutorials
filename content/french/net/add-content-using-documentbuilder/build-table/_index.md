---
title: Construire un tableau dans un document Word
linktitle: Construire un tableau dans un document Word
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment créer un tableau dans un document Word à l'aide d'Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/add-content-using-documentbuilder/build-table/
---
Dans ce didacticiel étape par étape, vous apprendrez à créer un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. Nous vous guiderons tout au long du processus et vous fournirons les extraits de code C# nécessaires. À la fin de ce guide, vous serez en mesure de créer un tableau avec une mise en forme et un contenu personnalisés à l'aide de la classe DocumentBuilder.

## Conditions préalables
Avant de commencer, assurez-vous que vous disposez des prérequis suivants :
- Bibliothèque Aspose.Words pour .NET installée sur votre système.

## Étape 1 : Créer un nouveau document
Pour commencer, créez un nouveau document en utilisant la classe Document :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : démarrer la table
Ensuite, utilisez la méthode StartTable de la classe DocumentBuilder pour commencer à construire la table :

```csharp
Table table = builder.StartTable();
```

## Étape 3 : Insérer des cellules et ajouter du contenu
Vous pouvez désormais insérer des cellules dans le tableau et y ajouter du contenu à l'aide des méthodes InsertCell et Write de la classe DocumentBuilder. Personnalisez le formatage des cellules selon vos besoins :

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Étape 4 : Terminer la ligne
Après avoir ajouté du contenu aux cellules de la première ligne, utilisez la méthode EndRow de la classe DocumentBuilder pour terminer la ligne :

```csharp
builder.EndRow();
```

## Étape 5 : Personnaliser le formatage des lignes
Vous pouvez personnaliser le formatage d'une ligne en définissant les propriétés des objets RowFormat et CellFormat :

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

## Étape 6 : Terminer la table
Pour compléter le tableau, utilisez la méthode EndTable de la classe DocumentBuilder :

```csharp
builder.EndTable();
```

### Exemple de code source pour créer une table à l'aide d'Aspose.Words pour .NET
Voici le code source complet pour créer une table à l’aide d’Aspose.Words for .NET :

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
Toutes nos félicitations! Vous avez appris avec succès comment créer un tableau dans un document Word à l'aide d'Aspose.Words pour .NET. En suivant le guide étape par étape et en utilisant le code source fourni, vous pouvez désormais créer des tableaux avec un formatage personnalisé.

### FAQ pour créer une table dans un document Word

#### Q : Qu'est-ce qu'Aspose.Words pour .NET ?

R : Aspose.Words for .NET est une puissante bibliothèque de traitement de documents qui permet aux développeurs de créer, lire, modifier et convertir des documents Microsoft Word par programmation dans des applications .NET. Il offre un large éventail de fonctionnalités pour travailler avec des documents Word, telles que la manipulation de texte, la création de tableaux, la protection de documents, le formatage, etc.

#### Q : Comment puis-je créer un tableau dans un document Word à l'aide d'Aspose.Words pour .NET ?

R : Pour créer un tableau dans un document Word à l'aide d'Aspose.Words for .NET, vous pouvez suivre ces étapes :
1.  Créez une nouvelle instance du`Document` classe et un`DocumentBuilder` objet.
2.  Utilisez le`StartTable` méthode du`DocumentBuilder`classe pour commencer à construire la table.
3.  Insérez des cellules dans le tableau et ajoutez du contenu à l'aide du`InsertCell` et`Write` méthodes du`DocumentBuilder` classe.
4.  Terminez la ligne en utilisant le`EndRow` méthode du`DocumentBuilder` classe.
5.  Personnalisez le formatage des lignes en définissant les propriétés du`RowFormat` et`CellFormat` objets.
6.  Terminez le tableau en utilisant le`EndTable` méthode du`DocumentBuilder` classe.
7. Enregistrez le document.

#### Q : Comment puis-je personnaliser la mise en forme du tableau et de ses cellules ?

 R : Vous pouvez personnaliser le formatage du tableau et de ses cellules en définissant diverses propriétés du`RowFormat` et`CellFormat` objets. Par exemple, vous pouvez ajuster l'alignement des cellules, l'orientation verticale et horizontale du texte, la hauteur des cellules, la hauteur des lignes, etc. En utilisant ces propriétés, vous pouvez obtenir l’apparence souhaitée pour le tableau et son contenu.

#### Q : Puis-je créer des tableaux complexes avec des cellules fusionnées et d’autres fonctionnalités avancées ?

 R : Oui, Aspose.Words for .NET fournit des fonctionnalités avancées pour créer des tableaux complexes, notamment la prise en charge des cellules fusionnées, des tableaux imbriqués et des dispositions de tableaux complexes. Vous pouvez utiliser le`MergeCells` méthode pour fusionner des cellules,`StartTable`méthode pour créer des tableaux imbriqués et d’autres méthodes pour obtenir la structure de table souhaitée.

#### Q : Aspose.Words pour .NET est-il compatible avec différents formats de documents Word ?

R : Oui, Aspose.Words for .NET est compatible avec différents formats de documents Word, notamment DOC, DOCX, RTF, etc. Il prend en charge à la fois les formats existants (DOC) et les formats XML modernes (DOCX) et vous permet de travailler avec des documents dans différents formats sans aucun problème.

#### Q : Où puis-je trouver plus d’informations et de documentation sur Aspose.Words pour .NET ?

 R : Vous pouvez trouver une documentation complète et des exemples de code sur[Références API](https://reference.aspose.com/words/net/). La documentation fournira des informations détaillées sur les fonctionnalités de la bibliothèque et comment les utiliser dans vos applications .NET.