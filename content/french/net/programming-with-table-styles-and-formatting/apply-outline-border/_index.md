---
title: Appliquer la bordure du contour
linktitle: Appliquer la bordure du contour
second_title: API de traitement de documents Aspose.Words
description: Guide étape par étape pour appliquer une bordure de contour à un tableau à l’aide d’Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

Dans ce didacticiel, nous vous guiderons pas à pas tout au long du processus permettant d'appliquer une bordure de plan à un tableau à l'aide d'Aspose.Words for .NET. Nous expliquerons le code source C# fourni et vous fournirons un guide complet pour vous aider à comprendre et à implémenter cette fonctionnalité dans vos propres projets. À la fin de ce didacticiel, vous comprendrez clairement comment manipuler les bordures de tableaux dans vos documents Word à l'aide d'Aspose.Words pour .NET.

## Étape 1 : Définir le répertoire des documents
Tout d’abord, vous devez définir le chemin d’accès à votre répertoire de documents. C'est ici que votre document Word est stocké. Remplacez « VOTRE RÉPERTOIRE DE DOCUMENTS » par le chemin approprié.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Étape 2 : Téléchargez le document
 Ensuite, vous devez charger le document Word dans une instance du`Document` classe.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Étape 3 : Accédez au tableau
 Pour appliquer une bordure de contour, nous devons accéder au tableau du document. Le`Table` la classe représente un tableau dans Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Étape 4 : Alignez le tableau au centre de la page
 Nous pouvons maintenant aligner le tableau au centre de la page en utilisant le`Alignment` propriété de la table.

```csharp
table. Alignment = Table Alignment. Center;
```

## Étape 5 : Effacer les bordures de tableau existantes
Pour commencer avec une nouvelle bordure de contour, nous devons d'abord effacer toutes les bordures existantes du tableau. Cela peut être fait en utilisant le`ClearBorders()` méthode.

```csharp
table. ClearBorders();
```

## Étape 6 : Définir une bordure verte autour de la table
 Nous pouvons maintenant définir une bordure verte autour de la table en utilisant le`SetBorder()` méthode pour chaque côté de la table. Dans cet exemple, nous utilisons une bordure de type "Single" d'une épaisseur de 1,5 points et de couleur verte.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Étape 7 : Remplissez les cellules avec une couleur d'arrière-plan
Pour améliorer la présentation visuelle du tableau, on peut remplir les cellules avec une couleur de fond de fond

idée. Dans cet exemple, nous utilisons une couleur vert clair.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Étape 8 : Enregistrez le document modifié
Enfin, nous enregistrons le document modifié dans un fichier. Vous pouvez choisir un nom et un emplacement appropriés pour le document de sortie.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Félicitation ! Vous avez maintenant appliqué une bordure de contour à un tableau à l'aide d'Aspose.Words pour .NET.

### Exemple de code source pour Appliquer la bordure de contour à l'aide d'Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Alignez le tableau au centre de la page.
	table.Alignment = TableAlignment.Center;
	//Supprimez toutes les bordures existantes du tableau.
	table.ClearBorders();
	// Définissez une bordure verte autour de la table mais pas à l'intérieur.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Remplissez les cellules avec une couleur unie vert clair.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à appliquer une bordure de contour à un tableau à l'aide d'Aspose.Words pour .NET. En suivant ce guide étape par étape, vous pourrez facilement intégrer cette fonctionnalité dans vos projets C#. La manipulation du formatage des tableaux est un aspect essentiel du traitement des documents, et Aspose.Words propose une API puissante et flexible pour y parvenir. Grâce à ces connaissances, vous pouvez améliorer la présentation visuelle de vos documents Word et répondre à des exigences spécifiques.