---
title: Insérer le tableau directement
linktitle: Insérer le tableau directement
second_title: Référence de l'API Aspose.Words pour .NET
description: Apprenez à insérer un tableau directement dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/insert-table-directly/
---

Dans ce didacticiel, nous allons apprendre à insérer directement un tableau dans un document Word à l'aide de Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure d'insérer des tableaux directement dans vos documents Word par programmation.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Étape 2 : création du document et du tableau
Pour commencer à travailler avec le tableau, nous devons créer un nouveau document et initialiser le tableau. Suivez ces étapes:

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// création de documents
Document doc = new Document();

// Créer le tableau
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 3 : Construire le tableau
Ensuite, nous allons construire le tableau en ajoutant des lignes et des cellules. Utilisez le code suivant comme exemple :

```csharp
// Créer la première ligne
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Créer la première cellule
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Dupliquer la cellule pour la deuxième cellule de la ligne
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Ici, nous créons une ligne avec le`AllowBreakAcrossPages` propriété définie sur`true` pour permettre le saut de page entre les lignes. Nous créons ensuite une cellule avec un arrière-plan coloré, une largeur fixe et un contenu textuel spécifié. Nous dupliquons ensuite cette cellule pour créer la deuxième cellule de la ligne.

## Étape 4 : Tableau d'ajustement automatique
Nous pouvons appliquer des ajustements automatiques au tableau pour le formater correctement. Utilisez le code suivant :

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Cette ligne de code applique un ajustement automatique basé sur des largeurs de colonne fixes.

## Étape 5 : Enregistrement du

  document modifié
Enfin, nous devons enregistrer le document modifié avec le tableau inséré directement. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour Insérer un tableau directement à l'aide d'Aspose.Words pour .NET 

```csharp
	// Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Nous commençons par créer l'objet table. Notez qu'il faut passer l'objet document
	//au constructeur de chaque nœud. C'est parce que chaque nœud que nous créons doit appartenir
	// à quelque document.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Ici, nous pourrions appeler EnsureMinimum pour créer les lignes et les cellules pour nous. Cette méthode est utilisée
	// pour s'assurer que le nœud spécifié est valide. Dans ce cas, un tableau valide doit avoir au moins une ligne et une cellule.
	// Au lieu de cela, nous gérerons la création de la ligne et de la table nous-mêmes.
	// Ce serait la meilleure façon de le faire si nous créions une table à l'intérieur d'un algorithme.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Nous pouvons maintenant appliquer tous les paramètres d'ajustement automatique.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Nous répéterions ensuite le processus pour les autres cellules et lignes du tableau.
	// Nous pouvons également accélérer les choses en clonant des cellules et des lignes existantes.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à insérer directement un tableau dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez insérer des tableaux directement dans vos documents Word par programmation. Cette fonctionnalité vous permet de créer et de personnaliser des tableaux en fonction de vos besoins spécifiques.