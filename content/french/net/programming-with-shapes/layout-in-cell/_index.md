---
title: Disposition dans la cellule
linktitle: Disposition dans la cellule
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir la disposition dans une cellule à l'aide d'Aspose.Words pour .NET avec ce guide complet. Parfait pour les développeurs cherchant à personnaliser des documents Word.
type: docs
weight: 10
url: /fr/net/programming-with-shapes/layout-in-cell/
---
## Introduction

Si vous avez toujours voulu affiner la disposition des cellules de votre tableau dans des documents Word par programmation, vous êtes au bon endroit. Aujourd'hui, nous allons découvrir comment définir la disposition dans une cellule à l'aide d'Aspose.Words pour .NET. Nous allons passer en revue un exemple pratique, en le décomposant étape par étape afin que vous puissiez suivre facilement.

## Conditions préalables

Avant de passer au code, assurons-nous que vous disposez de tout ce dont vous avez besoin :

1.  Aspose.Words for .NET : assurez-vous que la bibliothèque Aspose.Words for .NET est installée. Si ce n'est pas le cas, vous pouvez[téléchargez-le ici](https://releases.aspose.com/words/net/).
2. Environnement de développement : vous aurez besoin d'un environnement de développement configuré avec .NET. Visual Studio est un excellent choix si vous recherchez des recommandations.
3. Connaissance de base de C# : pendant que j'expliquerai chaque étape, une compréhension de base de C# vous aidera à suivre plus facilement.
4.  Répertoire de documents : préparez un chemin de répertoire dans lequel vous enregistrerez vos documents. Nous appellerons cela`YOUR DOCUMENT DIRECTORY`.

## Importer des espaces de noms

Pour commencer, assurez-vous d'importer les espaces de noms nécessaires dans votre projet :

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Décomposons le processus en étapes gérables.

## Étape 1 : Créer un nouveau document

 Tout d'abord, nous allons créer un nouveau document Word et initialiser un`DocumentBuilder` objet pour nous aider à construire notre contenu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Étape 2 : démarrer un tableau et définir le format des lignes

Nous allons commencer à construire un tableau et spécifier la hauteur et la règle de hauteur pour les lignes.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## Étape 3 : Insérer des cellules et remplir avec du contenu

Ensuite, nous effectuons une boucle pour insérer des cellules dans le tableau. Toutes les 7 cellules, nous terminerons la ligne pour en créer une nouvelle.

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Étape 4 : ajouter une forme de filigrane

 Maintenant, ajoutons un filigrane à notre document. Nous allons créer un`Shape` objet et définir ses propriétés.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, // Affichez la forme à l'extérieur de la cellule du tableau si elle doit être placée dans une cellule.
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Étape 5 : Personnaliser l'apparence du filigrane

Nous personnaliserons davantage l'apparence du filigrane en définissant ses propriétés de couleur et de texte.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Étape 6 : Insérer un filigrane dans le document

Nous trouverons la dernière exécution dans le document et insérerons le filigrane à cette position.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Étape 7 : optimiser le document pour Word 2010

Pour garantir la compatibilité, nous optimiserons le document pour Word 2010.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## Étape 8 : Enregistrez le document

Enfin, nous enregistrerons notre document dans le répertoire spécifié.

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## Conclusion

Et voilà ! Vous avez créé avec succès un document Word avec une disposition de tableau personnalisée et ajouté un filigrane à l'aide d'Aspose.Words pour .NET. Ce didacticiel visait à fournir un guide clair, étape par étape, pour vous aider à comprendre chaque partie du processus. Grâce à ces compétences, vous pouvez désormais créer par programmation des documents Word plus sophistiqués et personnalisés.

## FAQ

### Puis-je utiliser une police différente pour le texte du filigrane ?
 Oui, vous pouvez modifier la police en définissant le`watermark.TextPath.FontFamily` propriété à la police souhaitée.

### Comment ajuster la position du filigrane ?
 Vous pouvez modifier le`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` , et`VerticalAlignment` propriétés pour ajuster la position du filigrane.

### Est-il possible d'utiliser une image au lieu du texte pour le filigrane ?
 Absolument! Vous pouvez créer un`Shape` avec le genre`ShapeType.Image` et définissez son image à l'aide du`ImageData.SetImage` méthode.

### Puis-je créer des tableaux avec différentes hauteurs de lignes ?
Oui, vous pouvez définir des hauteurs différentes pour chaque ligne en modifiant le`RowFormat.Height` propriété avant d’insérer des cellules dans cette ligne.

### Comment supprimer un filigrane du document ?
 Vous pouvez supprimer le filigrane en le localisant dans la collection de formes du document et en appelant le`Remove` méthode.