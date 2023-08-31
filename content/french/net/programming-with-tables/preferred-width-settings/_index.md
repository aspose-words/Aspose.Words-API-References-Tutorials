---
title: Paramètres de largeur préférés
linktitle: Paramètres de largeur préférés
second_title: API de traitement de documents Aspose.Words
description: Découvrez comment définir les largeurs de cellule de tableau préférées dans un document Word avec Aspose.Words pour .NET.
type: docs
weight: 10
url: /fr/net/programming-with-tables/preferred-width-settings/
---

Dans ce didacticiel, nous allons apprendre à définir les paramètres de largeur préférés pour les cellules de tableau dans un document Word à l'aide de Aspose.Words pour .NET. Nous suivrons un guide étape par étape pour comprendre le code et implémenter cette fonctionnalité. À la fin de ce didacticiel, vous serez en mesure de spécifier différentes largeurs préférées pour les cellules de votre tableau dans vos documents Word.

## Étape 1 : configuration du projet
1. Lancez Visual Studio et créez un nouveau projet C#.
2. Ajoutez une référence à la bibliothèque Aspose.Words pour .NET.

## Etape 2 : Création du document et initialisation du générateur de document
Pour démarrer le traitement de texte avec le document et le générateur de documents, procédez comme suit :

```csharp
// Chemin d'accès à votre répertoire de documents
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// création de documents
Document doc = new Document();

// Initialiser le générateur de documents
DocumentBuilder builder = new DocumentBuilder(doc);
```

Assurez-vous de remplacer "VOTRE RÉPERTOIRE DE DOCUMENTS" par le chemin d'accès réel à votre répertoire de documents.

## Étape 3 : Construire le tableau avec les largeurs préférées
Ensuite, nous allons créer un tableau avec trois cellules qui ont des largeurs préférées différentes. Utilisez le code suivant :

```csharp
// Début du tableau
builder. StartTable();

// Insérer une cellule de taille absolue
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Insérer une cellule de taille relative (en pourcentage)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Insérer une cellule à taille automatique
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Fin de tableau
builder. EndTable();
```

Ici, nous utilisons le générateur de documents pour créer un tableau à trois cellules. La première cellule a une largeur préférée de 40 points, la deuxième cellule a une largeur préférée de 20 % de la largeur du tableau et la troisième cellule a une largeur préférée automatique qui s'ajuste

  en fonction de l'espace disponible.

## Étape 4 : Enregistrer le document modifié
Enfin, nous devons enregistrer le document modifié avec les paramètres de largeur préférés définis pour les cellules du tableau. Utilisez le code suivant :

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Assurez-vous de spécifier le chemin d'accès et le nom de fichier corrects pour le document de sortie.

### Exemple de code source pour les paramètres de largeur préférés à l'aide de Aspose.Words pour .NET 

```csharp
	//Chemin d'accès à votre répertoire de documents
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Insérez une ligne de tableau composée de trois cellules qui ont des largeurs préférées différentes.
	builder.StartTable();
	// Insérer une cellule de taille absolue.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Insérez une cellule de taille relative (pourcentage).
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Insérez une cellule de taille automatique.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Conclusion
Dans ce didacticiel, nous avons appris à définir les paramètres de largeur préférés pour les cellules de tableau dans un document Word à l'aide de Aspose.Words pour .NET. En suivant ce guide étape par étape et en implémentant le code C# fourni, vous pouvez personnaliser la largeur des cellules de votre tableau en fonction de vos besoins spécifiques dans vos documents Word.